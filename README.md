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

typing slow = 200ms
typing fast = 300ms

Performance:
- iphone 12pro max = 16 letters * 1000 = 16000
- with debouncing = 3 letters * 1000 = 3000

Debouncing with 200ms
- if difference between 2 key strokes is < 200ms - DECLINE API CALL
- > 200ms make an API call
