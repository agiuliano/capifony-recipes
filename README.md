#Capifony Recipes

Add some shortcut to your Capifony project

##Installation
Add the following to your composer.json

```json
"agiuliano/capifony-recipes": "dev-master"
```

##Usage
After you Capified your project, add the following to your Capfile if you want to add one recipe at time

```ruby
load 'vendor/agiuliano/capifony-recipes/recipes/ask_branch.rb'
```
otherwise, if you want to add all the recipes, you can add the following

```ruby
Dir["vendor/agiuliano/capifony-recipes/recipes/*.rb"].each {|file| load file }
```


____

#Recipes
The following section describes the recipes in the package and how to use them

##Git branch choice
When you deploy your application, Capifony just ask you which branch you want to deploy.

By default, it propose to you the current branch you are on.


##Parameters
When you setup your project, it'd be cool if Capifony automagically upload a specified parameters.yml on your server.

With this recipe you can tell Capifony which is you parameter file and when to upload it.
In particular, in deploy.rb or prod/staging/whatever.rb file you can write

```ruby
set :parameters_file, "parameters.yml"
after 'deploy:setup', 'upload_parameters'
```
`parameters_file` tells  which name your parameters file has whereas `after 'deploy:setup', 'upload_parameters'` explains when the task has to be performed.

You can also add a custom folder:
```ruby
set :parameters_dir, "app/config"
```


[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/agiuliano/capifony-recipes/trend.png)](https://bitdeli.com/free "Bitdeli Badge")

