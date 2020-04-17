---
layout: post
title:      "Final Project"
date:       2020-04-17 01:03:43 +0000
permalink:  final_project
---


For my final project I decided to build a trading application similar to [https://www.craigslist.org](http://) or [https://www.ebay.com/](http://). I have tried to choose projects which would push me to learn new aspects of the development process each time and challenge me to discover solutions to problems I have not faced in the past. Throughout the development of this application, I managed to tackle many new challenges, however, two in particular stand out as great learning experiences.

I knew that I wanted the user's state to be persisted over the course of a session, and although I am comfortable with how this works in a rails application, I wasn't sure where to start using rails as an API. I was able to get a login system working in my last project using rails as an API, so I had at least a foot in the door. As it turns out, the piece I was missing is rather simple and easy to understand.

```
get "current-user", to: "sessions#get_current_user
```

```
def get_current_user
 if logged_in?
  render json: current_user
 else
  render json: nil
 end
end
```

With the appropriate route and code above inside of our sessions controller, we then need to build a corresponding action for the front end to receive a response from this resource. Using the redux-thunk middleware to pass dispatch as a callback to our asynchronous fetch requests, we are able to write the following:

```
const getCurrentUser = () => {
 return dispatch => {
  fetch("http://localhost:3000/current-user", {
	credentials: "include"
  })
  .then(response => response.json())
  .then(json => dispatch({ type: "SET_CURRENT_USER", json }));
 }
}
```

And finally a case within our reducer to set the state:

```
const currentUser = (state = null, action) => {
 switch (action.type) {
  case "SET_CURRENT_USER":
   return action.json;
  default:
   return state;
 }
}
```

Next we need to be sure that this action fires everytime the page loads. To do this we simply take advantage of the `componentDidMount` method available to us in each react class component. We only want this action to fire once when the page is loaded so we ensure that our `App` component is a class component first and call our new action from within the `componentDidMount` method of `App`.

```
class App extends Component {
 componentDidMount() {
  this.props.getCurrentUser();
 }
 render() {
  ...
 }
}
```

Assuming we have properly exported, imported and connected to our redux store using react-redux we are now able to persist the state of our user during the session.

The second reasonable challenge I stumbled into involved figuring out how to employ the active storage gem effectively using rails as an API. Again, this is something I'm familiar with in rails applications, just not with a separated front end. Post requests seemed rather straight-forward previously, however, this problem forced me to learn a little more about the inner workings of these requests.

The first light-bulb moment came when I was sending the file to the back end using the header `"Content-Type": "application/json"` along with `JSON.stringify()` to package the object and received a content-disposition error. Within the error log was an enormous unicode string and I recognized this as the .jpeg file I was trying to send immediately. So I knew that the correct data was being sent, albeit in the wrong format.

After a few hours spent searching stack-overflow and researching fetch requests to gain a better understanding of what is expected to properly send this data, I found an insightful article, and although it wasn't a perfect solution to my particular problem, it conveyed enough information for me to form a solution which worked for me.

Here's a link to that article: [https://medium.com/@clarkjohnson_85334/uploading-photos-into-rails-6-activestorage-from-javascript-react-file-and-camera-653de99b183f](http://)

In short, we can do away with the headers and use the `FormData` class to package our data and send it to the API in place of JSON.

Despite this being my last project here at Flatiron, I look forward to picking up many more projects, continuing to learn and keeping my skills sharp. This has been a tremendously fulfilling journey. I am grateful for the Flatiron staff and instructors who have helped me through and I look forward to my final assessment.
