# aws_serverless

# validate template
cat template.yml | xargs -0 aws cloudformation validate-template --template-body
cat greeting.yml | xargs -0 aws cloudformation validate-template --template-body


# deploy template
aws cloudformation deploy --template-file template.yml --stack-name hello-serverless --capabilities CAPABILITY_NAMED_IAM
aws cloudformation deploy --template-file calculator.yml --stack-name calculatorStack --capabilities CAPABILITY_NAMED_IAM
aws cloudformation deploy --template-file greeting.yml --stack-name greetingStack --capabilities CAPABILITY_NAMED_IAM

# delete stack
aws cloudformation delete-stack --stack-name hello-serverless
aws cloudformation delete-stack --stack-name calculatorStack
aws cloudformation delete-stack --stack-name greetingStack