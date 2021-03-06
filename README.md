# MAPTY

###### \*Mapty is one project I learned from [Jonas Schmedtmann](https://www.udemy.com/share/101WfeAEYbdllRRHQH/).

## BRIEF

An app maps your workouts | [**DEMO**](https://howiework.github.io/mapty/)

<p>&nbsp;</p>

## KEYWORDS

OOP, Project planning, Geolocation API, Web Storage API, External libraries

<p>&nbsp;</p>

## FEATURES FIXME

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
- [x] Project planning
  - [x] User Stories
  - [x] Features
  - [x] Flowchart
  - [x] Architecture
- [x] Use Geolocation API
- [x] Display a map using Leaflet Library
- [x] Display a map marker
- [x] Render workout input form
- [x] Project architecture
- [x] Refactor based on architecture
- [x] Manage workout data (create Classes)
- [x] Create a new workout
- [x] Render workouts
- [x] Move to marker on click
- [x] Work with localStorage
- [x] Stage II preparation

### Stage II

- [ ] Add 'Edit/Delete' to a workout;
- [ ] Add 'Delete All' to all workouts;
- [ ] Workouts can be sorted by a certain field;
- [ ] Re-build Running and Cycling objects from local storage;
- [ ] Add realistic error and confirmation messages;
- [ ] Ability to position the map to show add workouts;
- [ ] Ability to draw lines and shapes instead of just points;
<!-- Only after Async Js section -->
- [ ] Geocode location from coordinates (expl. 'Run in Faro, Portugal);
- [ ] Display weather data for workout time and place;

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

```mermaid
graph TD
    Event1([Page loads])
    Event2([User clicks on map])
    Event3([User submits new workout])
    Event4([User clicks on workout in list])
    Render1[Render map on current location]
    Render2[Render workout on map]
    Render3[Render workout in list]
    Render4[Render workout form]
    Render5[Move map to workout location]
    Operation1(Get current location coordinates)
    Operation2(Load workouts from local storage)
    Operation3(Store workouts in local storage)

    Event1 -->|Async| Operation1
    Event1 --> Operation2

    Operation1 --> Render1
    Operation1 --> |After map loaded| Render2

    Operation2 --> |After map loaded| Render2
    Operation2 --> Render3

    Render1 -.Bind handler.-> Event2
    Event2 --> Render4
    Render4 -.Bind handler.-> Event3

    Event3 --> Render2
    Event3 --> Render3
    Event3 --> Operation3

    Render3 -.Bind handler.-> Event4
    Event4 --> Render5
```

### Architecture

![Mapty architecture](./Mapty-architecture.svg 'Mapty architecture')

```mermaid
classDiagram
    Workout <|-- Running
    Workout <|-- Cycling
    Workout : id
    Workout : date
    Workout : coords
    Workout : distance
    Workout : duration
    Workout: constructor()
    Workout: _getDescription()
    class Running{
      name
      pace
      cadence
      constructor()
      _calcPace()
    }
    class Cycling{
      name
      speed
      elevationGain
      constructor()
      _calcSpeed()
    }
    class App{
      map
      zoomLevel
      mapEvent
      workouts
      constructor()
      _getPosition()
      _loadMap(position)
      _showForm()
      _hideForm()
      _toggleElevationField()
      _newWorkout()
      _renderWorkoutMarker()
      _renderWorkout()
      _moveToPopup()
      _setLocalStorage()
      _getLocalStorage()
      reset()
    }
```
