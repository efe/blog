# [efe.me](https://efe.me)
A personal blog.

## Run on local

```sh
docker run --rm --volume="$PWD:/srv/jekyll:Z" --publish 4000:4000 jekyll/jekyll:builder jekyll serve --trace
```