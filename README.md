Next Lesson (no pun intended) https://nextjs.org/learn/basics/api-routes


Important NExt.js concepts

Pre-rendering: Generating HTML for each page in advance, instead of having it all done by client-side javascript
- Each generated HTML is accozited with the minimal JS code needed for that page. WHen a page is loaded by the browser, the JS runs and makes the page fully interactive (hydration)
 How to see it in action
 - Disable JS in your browser
 - Visit this page: https://next-learn-starter.vercel.app/
 - You should see that your App rendered without Javascript bc Next.js pre-rendered the app into static HTML. Other appraoches will tell you to enable Javascript

 *** My question: Does pre-rendering run any JS in the background? I think the answer is yes, and is described by hydration. What is the minimal amount of JS that gets run in hydration and do I have control over that? If so, that seems like a flaws design bc it could allow me to run JS even when a user has disabled JS

 2 Forms of Pre-rendering: Statis Generation and Server-side Rendering
 Static Generation: generates HTML at build time and reuses the pre-rendered HTML on each request
 - recommened to use this whenever possible bc your page can be built once and served by CDN
 Server-side Rendering: Generates HTML on each request
 - If your page shows frequently updated data and the page content changes on every request

 - pages are pre-rendered on every request when running in development mode.
 - You can choose which pre-rendering option you want on a page-by-page basis

Static Generation with Data: For pages that can only be generated after fetching external data at build time
*** WTF, this seems crazy
- In NExt.js when you export a page you can also export an async function cal getStaticProps
- getStatisProps runs at build time in production
- inside the function, you can fetch external data and send it as props to the page

Client-side rendering can also be used in situation where SEO is not relevant, the data is specific to a user and the page doesnt need to be pre-rendered.

SWR for data fetching
