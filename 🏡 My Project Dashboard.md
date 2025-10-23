### Active Projects & Deliverables

```dataview
TABLE status AS "Status", deadline AS "Deadline", length(filter(file.tasks, (t) => !t.completed)) AS "Tasks Left" FROM "1. Projects" WHERE contains(file.tags, "Project") SORT deadline ASC


```
### Recently Completed Tasks

```dataview
TASK
FROM "1. Projects"
WHERE completed
SORT completion ASC
LIMIT 15
```




```dataviewjs
dv.span("**📊 Stock Market Trading App Work Done**")

const calendarData = {
	year: 2025,
	colors: {
		green: ["#c6e48b", "#7bc96f", "#49af5d", "#2e8840", "#196127"],
		red: ["#ff9e82", "#ff7b55", "#ff4d1a", "#e73400", "#bd2a00"]
	},
	showCurrentDayBorder: true,
	defaultEntryIntensity: 4,
	intensityScaleStart: 1,  // 1 task completed
	intensityScaleEnd: 10,   // 10+ tasks completed
	cellSize: 200,            // 🔹 bigger cells (default is usually ~12)
	cellPadding: 3,          // 🔹 spacing between cells
	entries: [],
}

// loop through daily notes
for (let page of dv.pages('"1. Projects/Daily Notes"').where(p => p.file.name.match(/^\d{4}-\d{2}-\d{2}$/))) {
	// check if the note has the tag #Stock_Market_Trading_App
	if (page.tags && page.tags.includes("Stock_Market_Trading_App")) {
		calendarData.entries.push({
			date: page.file.name,
			intensity: 1, // fixed intensity (all marked equally)
			content: "📌", // marker icon
			color: "green",
		});
	}
}

// render larger calendar
renderHeatmapCalendar(this.container, calendarData, {
	cellSize: 18,   // bigger cells
	cellPadding: 3, // more spacing
	width: 1100,    // calendar width
	height: 220     // calendar height
})

```

