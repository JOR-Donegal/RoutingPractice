# Install Docker

On my Linux GNS3 install, I didn't have a working copy of Docker.

To confirm if you have a working copy

```
sudo docker run hello-world
```

If you cannot find Docker, follow the instructions to install Docker from [here](https://docs.docker.com/engine/install/ubuntu/).

## Permissions

Confirm your account can run Docker using&#x20;

```
docker run hello-world
```

If this works, you are done here, move to the next section.

If not, your user is not a member of the docker group.

Type&#x20;

```
more /etc/group
```

And verify your account is not a member of the docker group.

Type

```
sudo usermod -aG docker $USER
```

Check that your user account is now a member of the docker group using

```
more /etc/group
```

Confirm your account can run Docker using&#x20;

```
docker run hello-world
```
