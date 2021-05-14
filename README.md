# aragonjairus.com

This project is to launch a React site to AWS CloudFormation with CI/CD, using the [Serverless Framework](https://www.serverless.com/) 


#How to launch

---

### 1. Install AWS CLI, and configure with Access Key
   
1.a [Install CLI v2](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html)
   
1.b [Generate AWS Access Key](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_access-keys.html#Using_CreateAccessKey)
   
1.c [Configure CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html#cli-configure-quickstart-config)

---

### 2. Create a Github Repo with your site and a [Personal Access Token](https://docs.github.com/en/github/authenticating-to-github/creating-a-personal-access-token) with the following scope
- **repo** Full control of private repositories
- **admin:repo_hook** Full control of repository hooks

---

### 3. Get domain and SSL Certificate from Amazon
   
3.a [Register domain on Route53](https://docs.aws.amazon.com/Route53/latest/DeveloperGuide/domain-register.html)
   
3.b [Get SSL Certificate for that domain](https://docs.aws.amazon.com/acm/latest/userguide/gs-acm-request-public.html)

---

### 4. Create a config file

for example:

config.dev.json

```yaml
{
  "CloudFrontAlias": "aragonjairus.com",
  "CloudFrontAcmCertificateArn": "arn:aws:acm:us-east-1:888888888888:certificate/88888888-8888-8888-8888-888888888888",
  "GithubOwner": "shocknawe",
  "GithubRepo": "aragonjairus-frontend",
  "GithubOAuthToken": "ghp_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
}
```

### 5. run the command `npm run deploy`
