Docs

See https://docs.antora.org/antora/2.0/run-antora/#local-site-preview
and ./scripts/gen_doc.sh


Useful dev commands:

cd docs/book/

nvm use
yarn global add @antora/site-generator-default

nodemon --watch modules --ext adoc,yml --exec antora site.yml


OR

nodemon --watch modules --ext adoc,yml --exec "docker run -v `pwd`:/antora --rm -t antora/antora --stacktrace site.yml"

make a fake git repo in docs/book

git init .
touch .gitignore
git add .gitignore
git commit -m 'initialize repository'


NOTE: shouldn't be necessary

I have to create a “fake” git repository for the docs, since the docs live in my git project already

That's not true. You can use the playbook repository as a content repository. Couchbase does this (for their home page). See https://github.com/couchbase/docs-site/blob/master/production-antora-playbook.yml#L10-L12

In short, a) set the URL to ., set the branches filter to HEAD, and set the start_path to the folder to docs/book

(but this only works by moving site.yml to the root of the project...)