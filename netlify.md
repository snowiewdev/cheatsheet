# Site Deployment to Netlify

1. Create a netlify.toml file in the root and use this setting:
```
[build]
command = “CI= npm run build”
```

2. Push your code to Github and choose site deployment from netlify
