# Moira
![download](https://user-images.githubusercontent.com/107733608/174984742-9acd1b8b-ca3f-44dd-9186-0c2fa71827d4.jpg)

### Moira is a Finite State Machine with a simple API and Publisher that Apps can Subscribe to


### Requirements:
- JSON Initial State
- Transitions are in the form of JSON. Just specify what element needs transitioning, and its transition.
- Moira publishes the new state of your element to the subscriber that subscribes to that portion of the state.


#### Some Initial State for a Stop Light:
    {
        stoplight:{
          color: "red"
        }
    }

#### Transition Message:
    {
        stoplight:{
          color: "green"
        }
    }
    
#### State Machine API:
| Function          | Description                                                                                                | Params                                                                     | Example                     |
|-------------------|------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------|-----------------------------|
| init(json)        | sets the initial  application(s) state                                                                     | takes a JSON state object                                                  | {stoplight:{color:"red"}}   |
| get_state([json]) | gets the whole state if  no JSON is specified.<br>Or the local state if  specified                           | JSON is optional parameter                                                 | {stoplight:"color"}         |
| transition(json)  | Send a transition message  to the Moira State Machine.<br>Invalid transitions will  return an error message. | JSON state object is  necessary.<br>(Only change  one state object at a time) | {stoplight:{color: "blue"}} |
