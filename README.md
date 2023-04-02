### Guavo Web site

This site uses jekkyl to generate static site. Doing so makes it easy for me to quickly update the site with a markdown.
installing a ruby locally can be difficult. as such I have used docker to get the right ruby requirements.
here is the docker image that I have used:
also, inside the docker image, I have to run this command.

`bundle add webrick`
The docker image that was used to build the site is

`docker pull jekyll/jekyll`

To run the site I have used this command:

`docker run -it -v $(pwd):/site --net=host --entrypoint /bin/bash jekyll/jekyll`

In this command, I have net=host so that we can serve the site inside the docker container.

Once we are inside the container, we can go into
`/site`
run `bundle install` and
and run `bundle exec jekyll serve --host 0.0.0.0`
