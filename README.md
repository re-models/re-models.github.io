# RE-Models.github.io

Project Webpage of the SNFS/DFG Project ["How Far Does Reflective Equilibrium Take Us?"](https://re-models.github.io/).

This website is based on the [Jekyll](https://jekyllrb.com/) theme [Hydeout](https://github.com/fongandrew/hydeout). 

## Changing content

You can either change files directly on github or locally.  

The first possibility is sufficient for small changes. If you want to test changes locally before deploying them, you should follow the second suggestion. 

The second strategy comprises the following steps:

1. Clone the repo via `git clone git@github.com:re-models/re-models.github.io.git`.
2. Add changes to the files locally with an editor of your choice (e.g., [VS Code](https://code.visualstudio.com/)).
3. If necessary, test your changes locally. 
4. Git-add and commit the changes (see, e.g., this [intro](https://git-scm.com/docs/gittutorial)).
5. Push the changes into the repository (`git push`).

### Some hints

+ Updating publications site: Add the corresponding info to the file [publications.yml](https://github.com/re-models/re-models.github.io/blob/main/_data/publications.yml).
+ Updating project-description site: Change [index.html](https://github.com/re-models/re-models.github.io/blob/main/index.html).
+ Updating the team site: Change [team.html](https://github.com/re-models/re-models.github.io/blob/main/team.html).


## Running and testing locally 

1. Install jekyll and all requirements (👉 [jekyll-docs](https://jekyllrb.com/docs/)).
2. Clone the repo via `git clone git@github.com:re-models/re-models.github.io.git`.
2. In the terminal change into the directory of the repository's local copy.
3. Install necessary ruby-gems: `bundle update`
4. Run the local server: `bundle exec jekyll serve --livereload` 

## Deployment to github

The website will be build and deployed automatically with github actions via this [workflow](https://github.com/re-models/re-models.github.io/blob/main/.github/workflows/jekyll.yml) (see, e.g., [here](https://jekyllrb.com/docs/continuous-integration/github-actions/)). Besides committing the changes into the repository, nothing is needed to initiate the deployment process.

