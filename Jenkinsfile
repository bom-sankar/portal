
def bucket = 'portalfront'
def bucket2 = 'portallambda'
def region = 'us-east-2'
def functionName = 'myLambda'

node(){
    stage('Checkout'){
        checkout scm
    }

    stage('Build'){
        sh "zip lambda.zip lambda"
    }

    stage('Push'){
        sh "aws s3 cp index.html s3://${bucket}"
        sh "aws s3 cp lambda.zip s3://${bucket2}"
    }
	
	stage('Deploy'){
        sh "aws lambda update-function-code --function-name ${functionName} \
                --s3-bucket ${bucket2} \
                --s3-key lambda.zip \
                --region ${region}"
    }

    
}

