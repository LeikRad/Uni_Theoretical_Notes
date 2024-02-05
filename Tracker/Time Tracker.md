
```dataviewjs
// Get the full list
const pages = await dv.query(`
TABLE WITHOUT ID created AS "Day", working, gaming, break, other
FROM "Tracker/Days"
WHERE working
`)

if (pages.successful) {
	// Filter out the result you want, remember that the first column is 0
	const filtered = pages.value.values  
	// Present the result
	let workingSum = 0
	let gamingSum = 0
	let breakSum = 0
	let otherSum = 0
	filtered.forEach((arr) => {
		workingSum += Number(arr[1])
		gamingSum += Number(arr[2])
		breakSum += Number(arr[3])
		otherSum += Number(arr[4])
	})
	const total = ["Total", workingSum, gamingSum, breakSum, otherSum]
	filtered.push(total)
	dv.table(pages.value.headers, filtered)
	dv.paragraph("---")

	if ((workingSum + gamingSum + breakSum + otherSum) > 0) {

		const { default: {mermaidAPI} } = await import('https://cdn.jsdelivr.net/npm/mermaid@10/dist/mermaid.esm.min.mjs') 

		mermaidAPI.initialize({ startOnLoad: false, theme: 'base', themeVariables : {
			'darkMode' : true,
			'pie1' : '#0072BB',
			'pie2' : '#8FC93A',
			'pie3': '#BC2C1A',
			'pie4' : '#EE964B',
		} 
		}); 

		let el = dv.el("div", null);

		const graphDefinition = ` 
		pie 
			title Total Time Usage
			"Working" : ${workingSum}
			"Gaming" : ${gamingSum}
			"Break" : ${breakSum}
			"Other" : ${otherSum} 
		`
		const {svg} = await mermaidAPI.render("graphDiv", graphDefinition)
		el.innerHTML = svg;
	} else {
		dv.span("No hours to display graph")
	}
}
else
dv.paragraph("~~~~\n" + pages.error + "\n~~~~")
```
