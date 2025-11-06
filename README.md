# test-github-cache-bust

## Demo repo for testing/validating the behavior of GitHub's image-caching service (camo)

### What is this?

The cards on this page are [`github-readme-stats`](https://github.com/anuraghazra/github-readme-stats/) repo cards (adapted on a [fork](https://github.com/hesreallyhim/github-readme-stats-plus/) created and hosted by [hesreallyhim](https://github.com/hesreallyhim) in order to show more repo stats). They show the number of open Issues in this repo.

### OK, so what?

GitHub uses a service called [camo](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/about-anonymized-urls) for image caching and privacy/anonymization. That means that if you are serving an image with dynamic content, changes to the content may not be reflected right away. This repo illustrates different approaches to cache-busting so you can see for yourself what works or does not work at the current point in time.

## 1. Baseline (no cache-busting techniques applied)

### Usage

> [!tip]
> Create a new Issue in the repo. Do **not** include the word "nonce" anywhere in the body. See if and when the count on the card is actually updated.

```markdown
[![test-github-cache-bust](https://github-readme-stats-plus-theta.vercel.app/api/pin?username=hesreallyhim&repo=test-github-cache-bust&show_issues=true)](https://github.com/hesreallyhim)
```

<!-- BASELINE -->
[![test-github-cache-bust](https://github-readme-stats-plus-theta.vercel.app/api/pin?username=hesreallyhim&repo=test-github-cache-bust&show_issues=true)](https://github.com/hesreallyhim)
<!-- BASELINE-END -->

## 2. Nonce Query Parameter (image URL contains "nonce" query-parameter with random numerical value)

### Usage

> [!tip]
> The image URL below contains a query parameter `nonce` with a random number value. Create an Issue in this repository and write the word "nonce" somewhere in the body. This will trigger a GitHub Action that changes the query parameter value to some other "random" number. This is used to test whether changing query parameters is sufficient to bust the cache and refresh the image content.

<!-- NONCE -->
```markdown
[![test-github-cache-bust](https://github-readme-stats-plus-theta.vercel.app/api/pin?username=hesreallyhim&repo=test-github-cache-bust&show_issues=true&nonce=123456)](https://github.com/hesreallyhim)
```


[![test-github-cache-bust](https://github-readme-stats-plus-theta.vercel.app/api/pin?username=hesreallyhim&repo=test-github-cache-bust&show_issues=true&nonce=123456)](https://github.com/hesreallyhim)
<!-- NONCE-END -->


