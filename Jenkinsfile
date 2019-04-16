node {
    def app

    stage('Clone repository'){
        /* Let's make sure we have the repository cloned to our workspace */

        checkout scm
    }

    stage('Build image'){
        /* This builds the actual image; synonymous to
         * docker build on the command line */
       
        app = docker.build("piboonsak/example-app")

    }

   stage('Push image'){
        /* Finally, we'll push the image into Docker Hub */

        docker.withRegistry('http://registry.hub.docker.com', 'piboonsak'){
            app.push("latest")
        }
    }
}
