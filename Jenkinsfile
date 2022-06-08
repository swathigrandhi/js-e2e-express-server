pipeline{
    agent{label 'js_11'}
    stages{
        stage('source code') {
            steps {
                git branch:'main' , url:'https://github.com/Azure-Samples/js-e2e-express-server'
            }
        }
        stage ('build') {
            steps {
                sh ''' npm install
                       npm run build
                       npm pack
                       sudo apt install nodejs '''
            }
        }
    }
    post{
        success {
            archive '**/*.tgz'

        }
    }
}