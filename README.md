<h1> Node-handson-3<h1/>
<h4> How do you create a simple Express.JS application ? Ans. const express = require("express") const app = express() const port = 3000

app.get('/',(req,res) => {
res.send("Hello World !")
})
app.listen(port, () => {
console.log(`Example app listening on port ${port}`)
})
Implementation of all types of exports in backend application ? Ans. Named Export // imports // ex. importing a single named export import { MyComponent } from "./MyComponent"; // ex. importing multiple named exports import { MyComponent, MyComponent2 } from "./MyComponent"; // ex. giving a named import a different name by using "as": import { MyComponent2 as MyNewComponent } from "./MyComponent"; // exports from ./MyComponent.js file export const MyComponent = () => {} export const MyComponent2 = () => {}

Default export // import import MyDefaultComponent from "./MyDefaultExport"; // export const MyComponent = () => {} export default MyComponent; Create a middleware which will be applicable to all the routes ? Ans. const express = require("express"); const server = express();

 const middleware1 = (req,res,next) =>{
console.log("Hello this is middleware1")
 next()
}
const middleware2 = (req,res,next)=>{ console.log("Hello this is middleware2") }

//server.use(middleware1); //server.use(middleware2);

server.get("/",middleware1,(req,res) =>{ res.send("Hello World") //res.send({name:"Ranjeet", id:24}) //res.send("

Hello
") }) server.get("/user", middleware2 , (req,res) =>{ res.send("Hello User!") }) server.listen(30001, ()=>{ console.log("Server is running at port 3001") }) Implement CORS ? Ans CORS stands for Cross-Origin Resource Sharing. It allows us to relax the security applied to an API. This is done by bypassing the Access-Control-Allow-Origin headers, which specify which origins can access the API.
const cors = require('cors');
 app.use(cors({
origin: 'https://www.section.io' }));

const cors = require('cors');
app.use(cors({
origin: ['https://www.section.io', 'https://www.google.com/'] }));

app.use(cors({
origin: '*'
})) <h4/>
