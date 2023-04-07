# Jamstack

## JavaScript, APIs and Markup

Jamstack is a modern approach to the complexity of today's web, which is based on on-demand page generation.

Instead, it is based on leaner static HTML files, served from CDNs.

It uses JavaScript, API's and HMTL markup.

When displayed content needs to be dynamic, it exploits JavaScript.

Pros:

No server side processing > better performance > less energy consumption
Microservices > less surface area for attacks
Cheaper
Better development experience

Cons:
Short delays to live > live previews(Storyblok)
The bigger the site, the longer it takes to build

Interesting: [how to migrate from WordPress to Jamstack](https://www.smashingmagazine.com/2020/01/migration-from-wordpress-to-jamstack/)

## jamstacktools.org

Many third-party microservices are available to make Jamstack-based static pages dynamic.

## Static site generators (SSG)

The Jamstack approach means serving static HTML to users.

There are many popular tools to create static pages:

- Hugo (GO)
- Eleventy (JS) > very lean, only static HTML, no boilerplate JS shipped
- Next and Gatsby for React > ships static HTML, but hydrated as a React app > SPA-like feeling
- Astro > partial hydration possible > great for performance and very popular
- Nuxt > like Next, solid technical reasons > incremental SSG (partial build possible, caching already built components), community and developer experience

## Nuxt - Storyblok project

```
npx nuxi init nuxt-app
npm install
npm install @storyblok/nuxt
```

```JavaScript
export default defineNuxtConfig({
  modules: [["@storyblok/nuxt", { accessToken: "efkqPBVg5gMaL1f0M6D58wtt" }]],
});
```

## Storyblok

A headless CMS for content.

Via a REST API, we can consume the content anywhere else.

### Installation

```
choco install mkcert
mkcert -install
mkcert localhost

npm install -g local-ssl-proxy
local-ssl-proxy --source 3010 --target 3000 --cert localhost.pem --key localhost-key.pem
```

## Headless CMS

Content reusibility : content can be served to multiple pages, even websites via the same endpoints.

### Storyblok presets

A preset allows to set a block with default data.

## Static generation

`npm run dev` starts the development server but doesn't create a static file.

`npm run generate` creates a .output folder containing the static files.

As well as a dist folder, which is a sibling of .output for cross-platform compatibility.

`npm run preview` allows to preview the static website.

You can test the website's performance :

1. Incognito
2. Navigate to website (localhost:3000)
3. Dev tools > Lighthouse

## Deployment

1. Netlify
2. Add new site via GitHub repo
3. Change `npm run build` to `npm run generate`

(Netlify takes care of the building phase)
