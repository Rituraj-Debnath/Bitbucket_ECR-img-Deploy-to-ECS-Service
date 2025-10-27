Set these in Repository Settings > Pipelines > Repository variables:

AWS Credentials:
• AWS_ID - AWS Access Key ID
• AWS_KEY - AWS Secret Access Key (mark as secured)
• AWS_DEFAULT_REGION - AWS region (e.g., ap-south-1)
• AWS_ACCOUNT_ID - Your AWS account ID

Repository Info:
• S3BUCKET - S3 bucket name containing environment files
• BITBUCKET_BRANCH - Auto-provided by Bitbucket
• BITBUCKET_REPO_SLUG - Auto-provided by Bitbucket  
• BITBUCKET_BUILD_NUMBER - Auto-provided by Bitbucket

## AWS Prerequisites

IAM Permissions: The AWS user needs policies for:
• ECR (push/pull images)
• ECS (describe services, task definitions, register, update)
• S3 (read access to your bucket)

AWS Resources:
• ECR repository created
• ECS cluster: pgvibes-final
• ECS service: pgvibes-cx331-stage-service
• Task definition with containers named: backend-stage and worker-stage
• S3 bucket with .env file

Environment File:
• .env file stored in S3 at: s3://{S3BUCKET}/{REPO_SLUG}.env

## Bitbucket Settings
• Enable Pipelines in repository settings
• Docker service enabled (already in YAML)
