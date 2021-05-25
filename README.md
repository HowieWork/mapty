# MAPTY

###### \*Mapty is one project I learned from [Jonas Schmedtmann](https://www.udemy.com/course/the-complete-javascript-course/?referralCode=87FE8B1039A68106DEE5).

## BRIEF

An app maps your workouts | [**DEMO**](https://howiework.github.io/Mapty/)

<p>&nbsp;</p>

## KEYWORDS

OOP, Geolocation, External libraries, Project planning

<p>&nbsp;</p>

## FEATURES

### Interactive Map

- Indicate current location (Geolocation)
- Add new workouts
- Display all workouts on the map

### User Form

- Input distance, time, (pace, steps/minute), (speed, elevation gain)

### Interactive Workout List

- Display all workouts in the list
- Move map to workout location on click

### Workout data in the browser (Local storage API)

- Store workout data
- Read the saved data from local storage and display on page load

###### FIXME-highlight: NEW features I implemented (as challenges); \* FIXME-highlight: original features from the course;

<p>&nbsp;</p>

## TRACKING (TDL)

### Stage I

- [x] Project set-up
- [ ] Project planning
  - [x] User Stories
  - [x] Features
  - [x] Flowchart
  - [ ] Architecture
- [x] Use Geolocation API
- [ ] Display a map using Leaflet Library
- [ ] Display a map marker
- [ ] Render workout input form
- [ ] Project architecture
- [ ] Refactor based on architecture
- [ ] Manage workout data (create Classes)
- [ ] Create a new workout
- [ ] Render workouts
- [ ] Move to marker on click
- [ ] Work with localStorage
- [ ] Stage II preparation

### Stage II

- [ ] TBD

<p>&nbsp;</p>

## DETAILS

### User Stories

<!-- prettier-ignore-start -->
| WHO | WHAT | WHY |
| --- | ---- | --- |
| User 1 | Log **running** workouts with `location`, `distance`, `time`, `pace` and `steps/minut` | Keep a log of all my running |
| User 2 | Log **cycling** workouts with `location`, `distance`, `time`, `speed` and `elevation gain` | Keep a log of all my cycling |
| User 3 | See all my workouts at a glance | Easily track my progress over time |
| User 4 | See my workouts on a map | Check where I work out the most |
| User 5 | See all my workouts when I leave the app and come back later | Keep using the app over time |
<!-- prettier-ignore-end -->

### Flowchart

![Mapty flowchart](./Mapty-flowchart.svg 'Mapty flowchart')

### Architecture
