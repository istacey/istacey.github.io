istacey.github.io
=================

My personal profile page: a single static `index.html` with a photo in `images/profile.jpg`.

Live at:

- https://istacey.uk (canonical, hosted on a Raspberry Pi)
- https://istacey.github.io (GitHub Pages mirror)

`index.html` includes `<link rel="canonical" href="https://istacey.uk/">`, so search engines treat istacey.uk as the primary copy.

## Deploying

**GitHub Pages:** push to `master`.

**istacey.uk:** the Pi runs Apache with the site in `/var/www/html` (Let's Encrypt SSL; `www` redirects to the bare domain). It doesn't pull from GitHub, so copy changes over by hand:

```sh
tar cf - index.html images | ssh pi@raspberrypi.local \
  'sudo tar xf - -C /var/www/html --no-same-owner && sudo chmod -R a+rX /var/www/html'
```
