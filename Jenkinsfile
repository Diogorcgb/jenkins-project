pipeline {
    agent any
    
 parameters {
        string(name: 'FILE_NAME', defaultValue: 'myfile.txt', description: 'Nome do arquivo?')

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
                writeFile file: "${params.FILE_NAME}", text: 'hello write file'
            }
        }
        stage('Archive Artfact writefile File') {
            steps {
                archiveArtifacts artifacts: "${params.FILE_NAME}", followSymlinks: false
                
            }
        }
    }
 }
 