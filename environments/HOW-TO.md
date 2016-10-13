# Using CloudFormation

# Delete existing stack
$ aws --region ${AWS_REGION} cloudformation delete-stack --stack-name ${STACK_NAME}

# Wait till stack deletion is complete
$ aws --region ${AWS_REGION} cloudformation wait stack-delete-complete --stack-name ${STACK_NAME}

# Create stack
$ aws --region ${AWS_REGION} cloudformation create-stack \
    --stack-name ${STACK_NAME} \
    --template-body file://${WORKSPACE}/environments/template.json \
    --parameters file://${WORKSPACE}/environments/conf/${ENVIRONMENT_NAME}.json \
    --output text
    
# Wait till stack creation is complete
$ aws --region ${AWS_REGION} cloudformation wait stack-create-complete \
    --stack-name ${STACK_NAME}
    