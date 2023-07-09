## AWS CLI commands

Check AWS CLI version

    aws --version

Configure AWS credentials in Windows PowerShell

    aws configure

    AWS Access Key ID [None]: YOUR_ACCOUNT_ACCESS_KEY_ID
    AWS Secret Access Key [None]: YOUR_ACCOUNT_SECRET_ACCESS_KEY_ID
    Default region name [None]: us-east-1
    Default output format [None]:

List/check AWS credentials

    aws configure list

      Name                    Value             Type    Location
      ----                    -----             ----    --------
      profile                <not set>             None    None
      access_key     ****************LS5T shared-credentials-file
      secret_key     ****************DdjH shared-credentials-file
      region                us-east-1      config-file    ~/.aws/config
