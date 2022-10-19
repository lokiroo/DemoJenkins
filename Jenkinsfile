pipeline {
    agent { label 'master' }

    stages {
        stage('Test') {
            steps {
                echo 'Hello World'
            }
        }
        
        stage('Build') {
            steps {
                sh '''

                    mkdir /tmp/test_pipeline
                    echo "This is the content" >> /tmp/test_pipeline/test.txt
                    chmod 460 /tmp/test_pipeline/test.txt
                '''
            }
        }
        
        stage('Post-Build') {
            steps {
                sh '''
                    curl -X POST http://10.10.128.128:4440/api/41/job/30931caf-0c0d-4b52-8ee2-ae946e9f9287/run?authtoken=p3KuZ2M0mjf2U4Yg2o2VOMU0L4junNOo
                '''
            }
        }

    }
}
