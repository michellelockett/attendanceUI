# attendanceUI

![screen recording of app UI](http://g.recordit.co/oHYiuwjw27.gif)

## Stack 🥞
- React
- Axios
- Node/Express
- styled-components

## Service plans
- update Getting Started instructions to include how to run UI with API
- Redux for state management
- potentially Semantic-UI, to make main app styling cohesive
- add ability to actively hide the detail boxes (so that the rest of the dashboard is not cluttered)
- add `check all` feature to checkboxes
- do something if there's an error fetching datas

## Purpose
The attendanceUI is the face of a service intended to benignly check current student attendance (no LOG) in Hack Reactor's RPT program.

It is one part of a multifaceted dashboard tool.

## Getting Started
1. (run attendance API)
2. `npm install` to ensure your modules are up-to-date
3. `npm run build` - starts both webpack bundler && server
4. navigate to `http://127.0.0.1:3000/`

## How it works

Note: currently, there are only 5 cohorts at a time irl.

The static cohort data is intended to be used to render checkboxes and register the status of each checkbox.

When a checkbox is selected or deselected, the state is updated to reflect that.

When the `show attendance` button is clicked, a function is fired:
  1. All of the cohorts that were checked are saved to an array `attendanceArgs`, which is used to pass arguments to the attendance API (not currently linked to this repo).
  2. Then, `runAttendanceData` function is run.
  - this is supposed to use `runAttendanceData.js` API from the main app
  - the API is structured such that data retreival takes about 12s currently to make sure the limit isn't reached on GoogleSheets call frequency
  3. After attendance data is returned, relevant cohort boxes are rendered with the student attendance data arranged in a 2xN table
