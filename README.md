Docs


Run localy:

See https://docs.antora.org/antora/2.0/run-antora/#local-site-preview

nodemon --watch modules --ext adoc,yml --exec "docker run -v `pwd`:/antora --rm -t antora/antora --stacktrace site.yml"

