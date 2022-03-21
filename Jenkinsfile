pipeline {
    agent any

    stages {
        stage("setup local cluster") {
            steps {
                crc start
                eval $(crc oc-env)
                oc login -u developer https://api.crc.testing:6443
                
            }
        }
        stage("build") {
            steps {
                oc apply -f buildconfig-spring-petclinic.yaml
            }        
        }
        stage("deploy") {
            steps {
                echo 'Deploying the application'
            }
        }
    }
}