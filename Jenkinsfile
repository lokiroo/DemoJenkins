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
                    curl -X POST http://10.10.128.128:4440/api/41/job/4ec129cd-c9f6-4aec-97ff-a15e5993cc03/run?authtoken=p3KuZ2M0mjf2U4Yg2o2VOMU0L4junNOo
                '''
            }
        }

    }
}
