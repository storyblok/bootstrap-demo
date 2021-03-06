<p align="center">
  <h1 align="center">Storyblok Demo Website</h1>
</p>
<br><br>

## Intro

This is a demo website using Storyblok as CMS. With Storyblok you can decide to host your website on your own servers or to use Storyblok´s rendering service which is based on following project [github.com/storyblok/sinatra-boilerplate](https://github.com/storyblok/sinatra-boilerplate).

If you want to use the Storyblok´s fully hosted solution you can use this project as a starting point.

## Getting started

After cloning this repo:

1. Create a space in Storyblok and choose "Play with a demo"
2. Rename _token.js to token.js and insert your "theme" token (which you can find in the Storyblok dashboard).
![Theme token](https://monosnap.com/image/czAadgHCUblSMTzUHxq1rRV2FZ1tYB.png)
3. Fire up your dev environment
```
$ cd ./project && npm i && npm run dev
```
4. Add your dev environment 'http://localhost:4440/' to the environment settings

<img style="margin: 20px 0;" src="https://monosnap.com/image/wzRktNGxNXUJ1KEuS5f7WQsf2oqUnS.png" />

## Commands

In the background we're using `gulp` so you can change all the commands below and adopt them to your needs.
```
# Start you local dev environment on port 4440
$ npm run dev

# Build static assets (styles, scripts)
$ npm run build

# Sync your current state on the dev environment
# NOTICE: By default the environment is always live. To change this set 'environment' to 'dev' in `config.js`.
$ npm run deploy:dev

# Sync your current state on the live environment
$ npm run deploy:live
```

## Frequently Ask Questions

#### How can I load stories to create an overview for (news|articles|projects|...):

You can simply use following snippet to load all the stories from a specific folder according to the folder's slug like:

```
{% set newsitems from stories starts_with:'news', per_page: 3 %}
{% for news in newsitems.data %}
    {{ news.name }}
{% endfor %}
```

#### I used the Weblink/Storylink field type - How can I get the link in the template?
You will receive the actual path by using the `url` filter:

```
{{ blok.your_field_key | url }} <!-- Outputs a link, giving a link object -->
```

#### I uploaded a static file in the views/assets folder how can I reference that?
We've prepared the `asset_url` filter for that:

```
{{ 'assets/js/scripts.js' | asset_url }} <!-- Outputs the theme url -->
```

#### Is there a full documentation about those filters and other possibilities?

Sure! You can find them right here:

- [The Basics of Liquid](https://www.storyblok.com/docs/Rendering-Service/the-basics-of-liquid)
- [The Liquid of Storyblok](https://www.storyblok.com/docs/Rendering-Service/Theme-Documentation)
- [I want my own domain](https://www.storyblok.com/docs/Rendering-Service/Introduction)

<br>
<br>
<p align="center">
<img src="https://a.storyblok.com/f/39898/1c9c224705/storyblok_black.svg" alt="Storyblok Logo">
</p>
