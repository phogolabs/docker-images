# docker-images

### Public Docker Images

This repository contains a docker images used by CI

### Configure CI

```
fly -t phogo set-pipeline -p docker-images -c <(./script/merge-manifest) --load-vars-from=secrets.yml
```

### License

Apache 2.0 License
