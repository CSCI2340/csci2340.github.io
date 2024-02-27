# Art Generator Project
This is the GitHub Pages Site for CSCI 2340: Software Engineering, Art Generator Project at Brown University. <br />
**Members**: Malique Bodie, David Doan, Alina Kim, Gus LeTourneau, Yingjia Liu, Alexander Pratt, Morgann Thain, Haiyang Wang <br />
**Semester**: Spring 2024 <br />
**Current Project Repository:** [Art Generator Repository](https://github.com/newalina/art-gen)
**Contact for Feedback:** alina_kim@brown.edu

## Product Overview for February 29th, 2024

### Overall Product Description
The Art Generator Project is a user-driven, web-based art generation product that provides its user with modified images and videos using real-time data centered around social causes. Users can provide input of live camera input or generic stock photos, which will be modified depending upon data relating to climate change including rising temperatures, ice melting, deforestation, rising sea levels, and wildlife exctinctions. Users will be able to share their new art creations by file download or through social media. This project places an emphasis on security and privacy for user data that is used in the application.

### Front-End 

![Front End HLD](/img/Front-End-Figma.jpg)


User Component:
Communicates input between users and program
Features include: Mouse, keyboard, and Camera Detection
Security: Safe camera access
Technology: TSX

UI Component:
Acts as a central connection between the user and the processes. Displays output to the user component.
Features include: User Panel, Dataset Selection, Parameter Customization, Animations, 
Technology: NextJS, p5.js, three.js, canvas.js



Generative Component:
Combines user data and api data to generate and/or compute output
Risks: May be slow
Technology: TSX/Python

Gateway Component:
Connects the Front-End and Back-End
Technology: TypeScript




### Back-End

![Back End HLD](/img/Back-End-Figma.jpg)
Back-End Driver:
Combines user requests with real time data from external API to affect image processing.
Technologies: Python

API Caller:
Way of accessing external data relevant to user input selections
Technologies: Python

Database:
Stores recent data for faster computations.
Technologies: SQL



### Shared Components
Logging:
Provides logging data to user and programs to help catch bugs

Error Handling:
Provides accurate error codes to make errors more verbose and helps programmers to deduce bugs in code



### Team Member Expected Assignments
**Malique Bodie:**  <br />
**David Doan:** <br />
**Alina Kim:** <br />
**Gus LeTourneau:** <br />
**Yingjia Liu:**  <br />
**Alexander Pratt:** <br />
**Morgann Thain:** <br />
**Haiyang Wang:** <br />
