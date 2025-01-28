pipeline{
    agent any
    stages{
        stage('CleanUp Stage'){
            steps{
                echo "hello"
                deleteDir()
            }


        }

        stage('Clone Repo'){
            steps{
                git "https://github.com/jenkins-docs/simple-java-maven-app.git"
            }
        }

        stage('Build Stage'){
            steps{
                // As the files are present in Challenge2 Folder and controll is alredy in Challenge 2 No need to do dir         
                // dir('simple-java-maven-app'){
                    
                //     // sh "mvn clean install"
                // }

                bat 'mvn clean install'
            }
        }
        stage('Test'){
            steps{
                    // dir('simple-java-maven-app'){
                    echo "hello"
                    // sh "mvn test"
                // }
            }
        }
    }
}






pipeline{
    agent any

    stages{
        stage('CleanUp Stage'){
            steps{
                deleteDir()
            }
        }

        stage('File Clone'){
            steps{
                git 'https://github.com/jenkins-docs/simple-java-maven-app.git'
            }
        }

        stage('Build'){
            steps{
                bat 'mvn install cleaup'
            }
        }

        stage('Test'){
            steps{
                bat 'mvn test'
            }
        }

        stage('Exit'){
            step{
                echo 'Pipeline Successfull..!'
            }
        }
    }

}




pipeline{
    agent any

    parameters{
        booleanParam(defaultValue=false, description='this is a booleam parameter, enamble ??', name=myBoolVariable)
    }

    stages{
        stage('Build Stage'){
            steps{
                echo 'hello world using parameter ${param.myBoolVariable}'
            }
        }
    }
}





// Challenge 3

pipeline{

    agent any 

    parameters{

        // Checkbox
        booleanParam(defaultValue: false, description: "Confirm Deployement", name: "cnfDeployement")
        
        // custom input
        stringParam(defaultValue:"myDeployement1", description: "Deployement Name:", name: "dname" )
        
        // drop down
        choice(choice:["EU-WEST_2A", "EU-WEST_2B", "EU-WEST_2C"], description: "Deployement Environment" ,name: "DeployeEnv" )
    }

    stages{
        stage("CleanUp Stage"){
            steps{
                deleteDir()
                echo "CleanUp Stage Successfull..."
            }
        }

        stage("Build Stage"){
            steps{

                echo "Env name : ${dname}"
                echo "deploye Env choice : ${DeployeEnv}"
                echo "confirm deployement : ${cnfDeployement}"

                echo "Build Stage Successfull..."

            }
        }
    }
}