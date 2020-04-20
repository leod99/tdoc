# How to set up Jenkins pipeline for Bitbucket repo

1. Generate SSH key pair for jenkins on Linux 
   ~/.ssh/id_rsa
   ~/.ssh/id_rsa.pub
   
2. set public key on bitbucket repo,
   private key on Jenkins credentials
   
   
3. Generate user profile token on Jenkins server,
create pipeline item on Jenkins,

check generic-webhook-trigger, set random string for token, eg. s23sfRW43jrRxdvprn9h
Set repo URL(ssh:git@{git_repo_url}) & credential(the SSH private key) in Pipeline -> Definition(pipeline script from SCM) -> SCM(Git) -> Repositories


set webhook on bitbucket for the repo, as below format
https://{user_name}:{user_token}@jenkins.srv.westpac.com.au/generic-webhook-trigger/invoke?token=s23sfRW43jrRxdvprn9h

