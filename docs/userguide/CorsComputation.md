# Computation Cost for Cors/ SSL Err_PROT

A solution to this is getting a SSl certificate which can turn an http protocal to an https protocol. 
This way the front-end/lambda can talk to the blockchain. These are the steps to get an SSL protocol: 

1. Register Domain on Route53
   -  The cost depends on the type of ending or domain range you want. 
       [List of Domain Prices](https://d32ze2gidvkk54.cloudfront.net/Amazon_Route_53_Domain_Registration_Pricing_20140731.pdf)
      - The one that could be most common is .com since it is in the same realm of otRL, will cost about $12 USD.
      - The cost of renewing also in the document above varies on the ending of your domain name. 
2. Request Certificate on Amazon Certificate Manager
   - Requesting the domain name certificate
   ![
      - This should be no cost associated with it if the SSL/TLS certificate is used with one of the ACM integrated services: 
         - Elastic Load Balancing
         - API Gateway
         - Amazon CloudFront
         - AWS Amplify
         - more can be found at: https://docs.aws.amazon.com/acm/latest/userguide/acm-services.html
