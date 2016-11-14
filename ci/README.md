# docker-images

### Configuring the pipeline

The pipeline can be configure by using [fly] and `generate-manifest` script
that generates a pipeline manifests that depends on the current images.

```sh
fly -t phogo set-pipeline -p docker-images -c <(./script/generate-manifest) --load-vars-from=secrets.yml
```

MI
