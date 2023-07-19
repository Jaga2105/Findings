**1. Explain the difference between server-side rendering and client-side rendering in React.**

In a React application, there are two main ways to render the components: server-side rendering (SSR) and client-side rendering (CSR).

Server-side rendering (SSR) is when the initial render of a React application is done on the server. The server generates the HTML for the initial state of the application and sends it to the browser. When the JavaScript bundle loads, React takes over and the application continues to function as a SPA (Single-Page Application) on the client side.

This approach has a few benefits such as:

 Improved performance for search engines and users on slow connections
 
 Faster time-to-first-byte

Better accessibility for users who have JavaScript disabled

 Client-side rendering (CSR) is when the React application is rendered entirely in the browser, using JavaScript. The browser requests the JavaScript bundle from the server and then renders the components on the client side. This approach has the benefit of faster load times for users on fast connections and a more responsive user interface.

In general, CSR is the simpler option to implement and more popular, but SSR is a good choice for certain use cases, such as when SEO is a primary concern, or when the app is targeting users on slow internet connections.
It is also worth noting that, it is possible to have a hybrid approach between SSR and CSR which is called isomorphic or universal rendering. This approach allows to leverage the benefits of both SSR and CSR.



**2. What is CORS ?**

 CORS, which stands for Cross-Origin Resource Sharing, is a crucial web security mechanism. It allows web browsers to securely access resources (like fonts, images, or APIs) from different origins or domains.

✋ Why is CORS important? Well, imagine browsing a website and it needs to load data from a different domain. Without CORS, your browser would throw up a security error and block the request. CORS steps in to ensure these requests are made securely, while protecting your data from potential threats.

🔒 So, how does CORS work? When your browser makes a request to a different domain, it first sends an "origin" header specifying where the request originated. The server then checks this header and decides whether to allow or deny the request based on its CORS policy.

🌐 CORS policy typically includes information about which domains are allowed to access the server's resources. It can be set to permit requests from specific origins, or using wildcard characters, such as allowing requests from any origin.

💪 By enforcing CORS, web developers can strike a balance between allowing legitimate cross-origin requests and preventing unauthorized access to sensitive data.


**3. What i s debouncing ?**

A Debouncing Events in ReactJS will allow you to call a function that ensures that a time-consuming task does not fire so often. It’s a function that takes a function as a parameter and wraps that function in a closure and returns it so this new function displays the “wait for a bit” behaviour.

With debouncing we can make our app performant and by reducing the unwanted API calls.


**4. What is the use of Middleware Redux Thunk??**

Redux supports middleware, and middleware functions run between dispatching an action and the moment it reaches the reducer. Redux middlewares can be used for logging, routing, asynchronous actions, etc.

Plain redux doesn’t allow complex logic inside action functions, you can only perform simple synchronous updates by dispatching actions. This middleware extends its ability and lets you write complex logic that interacts with the store. Thunk doesn’t interfere with the action until it returns a function.

Thunk allows us to dispatch actions manually, which gives us the power to incorporate some logic or run some asynchronous code before dispatching an action. The function returned from action is called a thunk function which is called with two arguments : 
1. dispatch: It is a method used to dispatch actions, that can be received by reducers. 
2. getState: It gives access to store inside the thunk function.

![redux without thunk](https://github.com/Jaga2105/Findings/assets/110304276/be63b214-65f2-4d0b-ad85-27a9872555d1)
![redux-with-thunk](https://github.com/Jaga2105/Findings/assets/110304276/d3e9b82c-3456-4e6c-98ff-01f8132954f1)


**5. Difference between reducers and extraReducers in RTK.**

The reducers property both creates an action creator function and responds to that action in the slice reducer. The extraReducers allows you to respond to an action in your slice reducer but does not create an action creator function.

We will use reducers most of the time. We would use extraReducers when you are dealing with an action that you have already defined somewhere else. The most common examples are responding to a createAsyncThunk action and responding to an action from another slice.

If we create an action using createAsyncThunk function (which is imported from "@reduxjs/toolkit") we can handle loading, success & failure states.
