<h2>Choosing the base image</h2>
I used node-14 alpine as my base image due to its lightweight nature and thus it reduces the overall size of the final image.
<h2>Dockerfile directives used</h2>
I created two dockerfiles one for the backend code and another for the front-end:
<ul>
  <li>FROM: this specifies the base image</li>
  <li>WORKDIR: this specifies the working directory inside the container</li>
  <li>COPY: This is used to copy files from the local folders on my machine to the working directory in the container</li>
  <li>RUN:npm install: this is used to install the dependancies</li>
  <li>EXPOSE: this specifies the port number in which the container w</li>
  <li>CMD: used this to run the npm start command in order to start the development server</li>
</ul>
<p> I used these commands in the two dockerfiles each building different files</p>
<h2>Docker-compose Networking </h2>
<p>I defined a custom bridge network named yolo for the application. The networks section in my Docker Compose file is responsible for defining and configuring networks. </p>
<h2>Docker-compose volume definition and usage </h2>
<p>I defined a volume for my mongodb service in the docker compose file: I gave it the name mongodb_data</p>
<p>This helps me to persist data </p>
<h2>Git workflow used to achieve the task.</h2>
<ul>
  <li>Initially forked the repo</li>
  <li>Cloned the repository to my machine using git clone</li>
  <li>Made changes and committed them to github</li>
  <li>Pushed the changes using git push command</li>
  <li>Added this explanation.md file on github and pulled it to my local machine</li>
</ul>
