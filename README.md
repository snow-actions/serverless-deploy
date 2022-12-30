
# Serverless Deploy

Deploy [Serverless Framework](https://www.serverless.com/framework/docs).

## Usage

### AWS OpenID Connect (OIDC)

Required to set up ID provider and create an role for [OIDC](https://docs.github.com/en/actions/deployment/security-hardening-your-deployments/configuring-openid-connect-in-amazon-web-services).  
Set the role ARN to `role-to-assume`.

```yml
permissions:
  id-token: write
  contents: read
steps:
  - uses: actions/checkout@v3
  - uses: snow-actions/serverless-deploy/aws/oidc@v1.0.0
    with:
      role-to-assume: arn:aws:iam::123456789100:role/my-github-actions-role
      aws-region: us-east-2
```

See other options at [aws/oidc/action.yml](aws/oidc/action.yml)

### AWS Access Key

Not implemented.

## Supported

### Runners

- `ubuntu-*`
- `windows-*`
- `macos-*`
- `self-hosted`

### Events

- Any

## Dependencies

- Bash
- [aws-actions/configure-aws-credentials](https://github.com/aws-actions/configure-aws-credentials)
- [serverless - npm](https://www.npmjs.com/package/serverless)

## Contributing

Welcome.
