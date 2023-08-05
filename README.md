# podman-rpi
Podman resources for Raspberry Pi.

## Running Pods w/Systemd

1. Switch to the local user who will be executing the `podman` commands and set the necessary environmental variables.

   ```shell
   [unid@localhost:~]
   $ sudo su - <podmanuser>
   ...
   [podmanuser@localhost:~] 
   $ export XDG_RUNTIME_DIR=/run/user/$(id -ru)
   ```

2. In a directory on the host, clone this repository. For example:

   ```shell
   [podmanuser@localhost:/path/to/location]
   $ git clone --depth 1 https://github.com/adamhgriffith-uofu/podman-rpi.git
   ...
   [podmanuser@localhost:/path/to/location]
   $ cd podman-rpi
   ```

3. Start and enable the SystemD service.

   ```shell
   [podmanuser@localhost:/path/to/location/podman-rpi]
   $ make systemd/start
   ...
   $ make systemd/enable
   ...
   ```

4. For other available recipes see:

   ```shell
   [podmanuser@localhost:/path/to/location/podman-rpi]
   $ make help
   ...
   ```

## Additional Resources

* [How to run Kubernetes workloads in systemd with Podman](https://www.redhat.com/sysadmin/kubernetes-workloads-podman-systemd)
