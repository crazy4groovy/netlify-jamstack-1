# Netlify and Hexo notes

## Installing themes

If you install a hexo theme via git-clone, *be sure* to remove its `.git` folder; or it won't get committed/push into the site's git repo, and there will be unobvious build errors (unless you scrape the logs)!

## netlify-cms / Admin plugin

[netlify-cms](https://github.com/netlify/netlify-cms/blob/master/docs/quick-start.md) is a great little plugin, but with hexo there are a couple of gotchas from `hexo generate`. So I created an npm script (in package.json) called `admin-deploy-fix` that undoes all the hexo munging via the site generation (eg. .yml -> .json, index.html templatification).

In the Netlify project setting, I specify this build command:

`hexo generate && npm run admin-deploy-fix`
