# Snap for cookiecutter

1. Install Docker

1. Pull snapcraft

    ```bash
    docker pull snapcore/snapcraft
    ```

1. Create wrapper script for snapcraft

    ```bash
    #!/bin/bash
    
    sudo docker run --rm -v "$PWD":/build -w /build snapcore/snapcraft bash \
          -c "apt update && snapcraft $@"
    ```

1. Build the snap

    ```bash
snapcraft_wrapper
    ```

1. Install the snap

    ```bash
sudo snap install --devmode cookiecutter_1.6.0_amd64.snap 
    ```

1. Execute cookiecutter

    ```bash
cookiecutter
    ```

## Other useful commands

### Clean snap

```bash
snapcraft_wrapper clean cookiecutter -s pull
```
