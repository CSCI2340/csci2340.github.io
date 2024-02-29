# Art Generator Project
This is the GitHub Pages Site for CSCI 2340: Software Engineering, Art Generator Project at Brown University. <br />
**Members**: Malique Bodie, David Doan, Alina Kim, Gus LeTourneau, Yingjia Liu, Alexander Pratt, Morgann Thain, Haiyang Wang <br />
**Semester**: Spring 2024 <br />
**Current Project Repository:** [Art Generator Repository](https://github.com/newalina/art-gen)<br />
**Contact for Feedback:** alina_kim@brown.edu

## Product Overview for February 29th, 2024

### Overall Product Description
The Art Generator Project is a user-driven, web-based art generation product that provides its user with modified images and videos using real-time data centered around social causes. Users can provide input of live camera input or generic stock photos, which will be modified depending upon data relating to climate change including rising temperatures, ice melting, deforestation, rising sea levels, and wildlife exctinctions. Users will be able to share their new art creations by file download or through social media. This project places an emphasis on security and privacy for user data that is used in the application.

### Product Specifications
* The interface will support a share button that allows the user to specify the desired output format ie. gif, image, or short video, as well as a destination that includes social media sites and a local download option. <br />
* The web application will take user web cam data as input and generate various stylized, data-specific outputs. The generated output will be a creative representation of environmental data, using color, motion, and intensity to represent various trends in the data. <br />
* The user will have the ability to choose from multiple environmental datasets including global temperature, water level, precipitation rates, etc… which will each generate different data-specific outputs that reflect creative renderings of the environmental data trends. <br />
* The main user interface will be a web application that takes user inputs through user panel and generate outputs(image/ gif/ video) accordingly. <br />
* The interface will generate texts explaining how we generate the outputs(which dataset is employed) and the meaning behind them(what’s the environmental or social impact) base on user’s dataset choice. <br />
* The interface will include a user panel such that the user can adjust parameters or choosing between datasets to generate specific output they desire. <br />


### Front-End 

![Front End HLD](/img/Front-End-Figma.jpg)


#### User Component:
Communicates input between users and program <br />
Features include: Mouse, keyboard, and Camera Detection <br />
Security: Safe camera access <br />
Technology: TSX <br />

#### UI Component:
Acts as a central connection between the user and the processes. Displays output to the user component. <br />
Features include: User Panel, Dataset Selection, Parameter Customization, Animations, <br />
Technology: NextJS, p5.js, three.js, canvas.js <br />

#### Generative Component:
Combines user data and api data to generate and/or compute output <br />
Risks: May be slow <br />
Technology: TSX/Python <br />

#### Gateway Component:
Connects the Front-End and Back-End <br />
Technology: TypeScript <br />

### Back-End

![Back End HLD](/img/Back-End-Figma.jpg)
#### Back-End Driver:
Combines user requests with real time data from external API to affect image processing. <br />
Technologies: Python, OpenCV <br />

#### API Caller:
Way of accessing external data relevant to user input selections <br />
Technologies: Python <br />

#### Database:
Stores recent data for faster computations. <br />
Technologies: SQL <br />



### Shared Components
#### Logging:
Provides logging data to user and programs to help catch bugs <br />

#### Error Handling:
Provides accurate error codes to make errors more verbose and helps programmers to deduce bugs in code <br />



### Team Member Expected Assignments
**Malique Bodie:** Backend - Backend/Database Interaction <br />
**David Doan:** Backend - Backend/Frontend Communication <br />
**Alina Kim:** Frontend - Art Generation Computation, UI <br />
**Gus LeTourneau:** Frontend - Backend/Frontend Communication, UI <br />
**Yingjia Liu:** Frontend - Output to File, External Media Sites  <br />
**Alexander Pratt:** Backend - External API Interfacing, Storage, and Usage <br />
**Morgann Thain:** Backend - Backend Driver <br />
**Haiyang Wang:** Frontend - User Input and Security <br />
