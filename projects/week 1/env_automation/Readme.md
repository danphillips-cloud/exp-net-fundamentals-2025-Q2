## How to deploy

### Verify Your AWS Credentials

```sh
aws sts get-caller-identity
```

### Run Deploy Script

```sh
cd projects\env_automation
chmod u+x ./bin/deploy
./bin/deploy
```

> You only need to chmod the file once to make it executable.