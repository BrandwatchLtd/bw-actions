# bw-actions
A collection of reusable Github Actions, for you to use in your projects.

## Actions

### Deploy Techdocs

The `deploy-techdocs` action will build your [techdocs](https://brandwatch.dev/docs/default/component/techdocs) and push them to an [aws-S3](https://aws.amazon.com/s3/) bucket.

```yaml
    steps:
      - uses: BrandwatchLtd/bw-actions/deploy-techdocs@main
        with:
          entity: <your-service-name>
          TECHDOCS_S3_BUCKET_NAME: ${{ secrets.TECHDOCS_S3_BUCKET_NAME }}
          AWS_TECHDOCS_ACCESS_KEY_ID: ${{ secrets.AWS_TECHDOCS_ACCESS_KEY_ID }}
          AWS_TECHDOCS_SECRET_ACCESS_KEY: ${{ secrets.AWS_TECHDOCS_SECRET_ACCESS_KEY }}
          AWS_TECHDOCS_REGION: ${{ secrets.AWS_TECHDOCS_REGION }}
```

`your-service-name` is the name of the [backstage](https://github.com/BrandwatchLtd/katalog/tree/main/services) service you want to build a doc for.

Here is [an example of workflow](https://github.com/BrandwatchLtd/WebappService/blob/main/.github/workflows/techdocs.yml) using techdocs.
