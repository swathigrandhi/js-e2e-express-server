pipeline{
    agent{label 'js_11'}
    stages{
        stage('source code') {
            steps {
                git  'https://github.com/Azure-Samples/js-e2e-express-server'
            }
        }
        stage{
            steps{
                sh ''' npm install
                       npm run build
                       npm pack'''
            }
        }
    }
    post{
        success{
            archive '**/*.tgz'

        }
    }
}