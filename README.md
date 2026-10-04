# lasiestaamericana.com — retired source archive

The hosted website was retired on 4 October 2026. Its AWS website infrastructure and web DNS records have been removed; no retirement notice or replacement site is hosted. Domain registration and this source repository are retained.

SiestaCMS (siestacms.com) is a separate application and remains online with its existing configuration.

The instructions below are retained as historical development documentation. Do not run deployment commands against the retired service without explicitly planning a new deployment. There are no GitHub Actions deployment workflows in this repository as of retirement. Recovery material is held privately by the owner.

## Historical development prerequisites

- Docker
- Docker Compose
- AWS credentials in ~/.aws or environment variables
  
Environment variables can be defined inside your shell session using `export VAR=value` or setting them in `.env` file. See `env.example` for more information.

## Usage

Create .env file based on .env.example:

    $ make envfile ENVFILE=env.example

Install dependencies:

    $ make deps

Test:

    $ make test

Build:

    $ make build

Historical AWS deployment command (would recreate infrastructure; do not use for routine development):

    $ make deploy-dev

Clean your folder

    $ make clean

## How to use the CMS

1. Create a new file (for example with name `my-post.html`) under `/posts` with this structure:

        <head>
            <title>Hey! This is a new post</title>
            <date>01/01/2020</date>
            <summary>This summary will appear in the index</summary>
            <image></image>
        </head>
        <body format="html">
            <![CDATA[
                <p>This is my first paragraph.</p>
            ]]>
        </body>
2. Deploy the service.
3. The post will appear in the index page and under `/posts/my-post.html`
4. Done!

## Acknowledgements

- Thanks to @amaysim-au for their great solution for Serverless & Docker: https://github.com/amaysim-au/docker-serverless. Pretty cool stuff :)