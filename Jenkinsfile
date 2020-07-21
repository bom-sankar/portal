
def bucket = 'portalfront'

node('slaves'){
    stage('Checkout'){
        checkout scm
    }


    stage('Push'){
        sh "aws s3 cp index.html s3://${bucket}"
    }

    
}

