# JSON SERVER :sunglasses:

- JSON Server REST API mocking based on plain JSON

## Description :books:

[JSON Server](https://github.com/typicode/json-server) provides REST API mocking based on plain JSON.
This is a [docker](https://www.docker.io) image that eases setup.

## Startup :heavy_check_mark:

This docker image is available as a [trusted build on the docker index](https://hub.docker.com/repository/docker/jcmds/jsonserver/),
so there's no setup required.
Using this image for the first time will start a download automatically.
Further runs will be immediate, as the image will be cached locally.

The recommended way to run this container looks like this:

```bash
$ docker run -d -p {OutsidePort}:80 -v  {AbsolutePathToJsonFile}:/data/db.json jcmds/jsonserver
```

The above example exposes the JSON Server REST API on port 80, so that you can now browse to **http://localhost/**

### Help

You can supply any number of JSON Server arguments that will be passed through unmodified.

```bash
$ docker run -it --rm jcmds/jsonserver --help
```

### JSON source :construction:

If you mount a file to `/data/db.json` (as in the above example),
it will automatically be used as the plain JSON data source file.

A sample file could look like this:

```json
{
  "posts": [
    { "id": 1, "body": "foo" },
    { "id": 2, "body": "bar" }
  ],
  "comments": [
    { "id": 1, "body": "baz", "postId": 1 },
    { "id": 2, "body": "qux", "postId": 2 }
  ]
}
```

## Run in Kubernetes ⚡
- Change configMap in k8sdeploy.yaml
- exec in terminal: kubectl apply -f k8sdeploy.yaml
