# artifacthub-compose

docker compose setup to spin up [ArtifactHub](https://artifacthub.io/) for local testing

## Run

- Clone this project using `git clone --recursive`
  - if it's already cloned without `--recursive` flag, run `git submodule update --init --recursive` to pull Artifact Hub source to submodule folder
- `docker-compose up`

and the hub is accessible at `http://localhost:8000`

log in credentials

```
username: demo@artifacthub.io
password: changeme
```
