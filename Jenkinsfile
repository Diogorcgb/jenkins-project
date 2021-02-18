pipeline {
    agent any
    
    environment{
        FILE_NAME = 'newfile.txt'
        
    }
    

    stages {
        stage('Parallel'){
        parallel {
            stage('Stage A'){
                agent any
                steps{
                    echo"On Stage A"
                    
                }
            }
            stage('Stage B'){
                agent any
                steps{
                    echo"On StageB"
                    
                }
            }
        }
            
        }
        stage('Echo Hello World') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Create Hello File') {
            steps {
                writeFile file: "$FILE_NAME", text: 'hello write file'
            }
        }
        stage('Archive Artfact writefile File') {
            steps {
                archiveArtifacts artifacts: "$FILE_NAME", followSymlinks: false
                
            }
        }
    }
 }
 