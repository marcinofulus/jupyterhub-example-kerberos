# jupyterhub-example-kerberos

A proving ground for configuring JupyterHub to work with Kerberos.

This project exists to help you (and us) learn how JupyterHub and Kerberos can interoperate. It will never provide an out-of-the-box, production-ready experience.

At the moment, it is very much a work in progress. If you have experience configuring JupyterHub with Kerberos, please jump in and help us out!

## Goals

* [x] Two local users (principals), `alice` and `bob` can successfully log into JupyterHub when it is configured with PAM backed by Kerberos.
* [x] The two users automatically receive a Kerberos ticket granting ticket (TGT) upon Hub login.
* [x] The on-disk credential cache (ccache) for each user is read-write accessible by the owner alone and without additional user action.
* [x] The users can refresh the TGT with the `kinit` command.
* [ ] The users can request a ticket for a service princpal named `service` using the `kvno` command.
* [ ] TODO: keytabs?
* [ ] All other JupyterHub functions behave as expected: starting notebook servers, stopping notebook servers, logging out, admin functions, etc.
* [ ] The above works with the following spawners:
    * [x] default spawner
    * [ ] sudospawner
    * [ ] your contribution welcome!

## Running

To start a KDC container and a separate JupyterHub container with the default spawner configured:

```
docker-compose up
```

To start the KDC and JupyterHub with the sudospawner configured:

TODO
