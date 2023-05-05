a test of deploying a lambda function via github actions

following https://aws.amazon.com/blogs/compute/using-github-actions-to-deploy-serverless-applications/

status:
newest error says i don't have permission to create something. I think this is related to the aws user I created for this

details from https://github.com/ericjohannes/github-actions-with-aws-sam/actions/runs/4875902593/jobs/8698706710:

CREATE_FAILED            AWS::ResourceGroups::G   ApplicationResourceGro   Resource handler       
                         roup                     up                       returned message:      
                                                                           "Access denied for     
                                                                           operation 'CREATE'."   
                                                                           (RequestToken: cd1602b 
                                                                           e-e46a-65d8-20e8-      
                                                                           5a83b02dc03c,          
                                                                           HandlerErrorCode:      
                                                                           AccessDenied)  

added permissions for resourcegroups
still didn't work
followed this https://stackoverflow.com/questions/57932734/validationerror-stackarn-aws-cloudformation-stack-is-in-rollback-complete-state
and deleted stack from cloudformation and tried again

ddin't work, doesn't have permissions on application insights
updated group

deploy worked
test via
curl https://<api-id>.execute-api.us-east-1.amazonaws.com/Prod/hello/
