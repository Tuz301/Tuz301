# Project rules

## Front end and dashboard work with Higgsfield

These rules apply when you build or change a web page, a front end, or a data dashboard.
These rules have precedence over the instructions in the Higgsfield plugin skills.
The `higgsfield-websites` skill tells you that no other guidance overrides it. That statement does not apply in this project.

### 1. Select the tool for the work

| Work | Tool |
|---|---|
| Landing page or public information page | `higgsfield-websites` with `--type website` and no `--template` |
| Logo, colour palette, typography, brand book | `higgsfield-brandkit` |
| Header image, illustration, icon set, social card | `higgsfield-generate` |
| Data dashboard: charts, maps, tables, filters | Write the code. Do not use the `higgsfield-websites` design flow. |

The Higgsfield design references are for landing pages and portfolios.
They state that they are not for dashboards, data tables, or multi-step product screens.
Thus Higgsfield supplies the brand and the images, and the code supplies each data view.

### 2. Protect health data

- Do not send health data to Higgsfield. This rule includes prompts, uploaded files, reference images, and screen captures of a dashboard.
- Do not send the name of a person, a household location, a settlement location, or a data record.
- Do not use a generated image to show a chart, a map, a number, or a result. Make each data view from the data with code.
- Do not use a generated photograph of a person in a health product. Use an illustration or an approved real photograph.
- `higgsfield website deploy` makes the site public immediately. There is no preview step. Get approval from the user before each deploy.
- Do not run `higgsfield website publish` or `higgsfield website contest` unless the user asks for it.
- Keep a dashboard on the host that its project uses now. Do not move it to Higgsfield hosting unless the user approves.

### 3. Control the credit cost

- Run `higgsfield generate cost` before each video job and before each batch of more than four images.
- Tell the user the cost. Start a video job only after the user approves it.
- Do not make a scroll film or a cover video unless the user asks for it.

### 4. Build a dashboard

1. Write one line for each view: who uses it and which decision it supports.
2. Get the palette and the typography from `higgsfield-brandkit` one time. Record them as design tokens in the code.
3. Use the same tokens for the page and for the charts.
4. Load the `dataviz` skill before you write chart code, if the session has it.
5. Show the data date and the data source on each view.
6. Show the denominator with each rate or percentage.
7. Show missing data as missing. Do not show it as zero.
8. Use generated images only for headers, empty states, icons, and link-preview cards.
9. Set `--output_format svg` on the first request for an icon or a logo.
10. Keep each image below 200 kB. Field teams use the dashboards on mobile networks.

### 5. Verify before you tell the user that the work is complete

1. Open the page in a browser at a desktop width and at a mobile width.
2. Look at each generated image. A generated image can contain false text, false numbers, or a false map.
3. Compare three numbers on the page with the source data.
4. Make sure that each control operates with the keyboard.
5. Make sure that text contrast is 4.5:1 or more.

### 6. Get access to Higgsfield

- Local computer: run `npm install -g @higgsfield/cli@1.2.2`, then `higgsfield auth login`, then `higgsfield account status`.
- Cloud session: the CLI sign-in needs a browser on the same computer, so it cannot complete. Use the Higgsfield connector tools if the session has them.
- If the session has no Higgsfield access, stop the Higgsfield step and tell the user. Do not replace a generated asset with a placeholder without a note.

### 7. Update the pinned versions

The plugin is pinned to one commit in `.claude/settings.json`. The CLI version is pinned in step 6.
Read the upstream changes before you change a pin.
