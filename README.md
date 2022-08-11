# Docker Desktop Local Server Config for Kirby CMS


## What’s this?

This is a ready-to-use Docker configuration that spawns a local development server with Apache and ImageMagick.

Multiple Kirby projects can live in the folders adjacent to this repo and will automatically be reachable as virtual hosts like this: `http://foldername.localhost`

## How to install

You’ll need to get [Docker Desktop](https://www.docker.com/products/docker-desktop/) first.

This Docker configuration assumes the following folder structure:

```
(parent folder)
├── docker-kirby-server
│  └── (contents of this repo) ←←←
├── mykirbyproject
├── mykirbyotherproject
└── …
```

You can access your Kirby projects in the browser by appending `.localhost` to the folder name, e.g.  `http://mykirbyproject.localhost` and `http://mykirbyotherproject.localhost`

As a fallback, the standard `http://localhost` address shows the content of the `_localhost` folder in this repository.

The local virtual hosts should work with Firefox out of the box. For other browsers, you may have to append each virtual host to your `/etc/hosts` file like this:

```
127.0.0.1	mykirbyproject.localhost
127.0.0.1	myotherkirbyproject.localhost
…
```

## How to run

Point your terminal to this repository and run  `docker-compose up`.
