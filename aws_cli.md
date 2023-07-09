## AWS CLI commands

Check AWS CLI version

    aws --version

Configure AWS credentials in Windows PowerShell

    aws configure

    AWS Access Key ID [None]: YOUR_ACCOUNT_ACCESS_KEY_ID
    AWS Secret Access Key [None]: YOUR_ACCOUNT_SECRET_ACCESS_KEY_ID
    Default region name [None]: us-east-1
    Default output format [None]:

List/check AWS configuration

    aws configure list

      Name                    Value             Type    Location
      ----                    -----             ----    --------
      profile                <not set>             None    None
      access_key     ****************LS5T shared-credentials-file
      secret_key     ****************DdjH shared-credentials-file
      region                us-east-1      config-file    ~/.aws/config

AWS ECR Login - this will output the password string which has to be piped (passed as input) to docker login command

    aws ecr get-login-password --region us-east-1

AWS ECR Docker login (running this command should return 'Login Succeeded' message.

    aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 172763042044.dkr.ecr.us-east-1.amazonaws.com

    172763042044.dkr.ecr.us-east-1.amazonaws.com - registry domain

Tagging docker images before pushing them into AWS ECR - tagging the image creates a new image with the name - 'registryDomain/image_name:tag'. This is what tells that the image has to be pushed to AWS ECR and not into DockerHub.

    docker tag myapp:latest 172763042044.dkr.ecr.us-east-1.amazonaws.com/myapp:latest

Docker push command to push the image to AWS ECR

    docker push 172763042044.dkr.ecr.us-east-1.amazonaws.com/myapp:latest

