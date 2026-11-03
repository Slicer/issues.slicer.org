# issues.slicer.org

Netlify site that redirects https://issues.slicer.org to the
[Slicer GitHub issues](https://github.com/Slicer/Slicer/issues), keeping the path:

| Request | Redirects to |
|---|---|
| `https://issues.slicer.org/` | `https://github.com/Slicer/Slicer/issues/` |
| `https://issues.slicer.org/123` | `https://github.com/Slicer/Slicer/issues/123` |

The redirect is defined in [`_redirects`](_redirects) as a forced `301`, so
`index.html` is never served; it only exists because Netlify will not deploy an
empty site.

## Deployment

- Netlify site with no build command and the repository root as the publish directory.
- Custom domain `issues.slicer.org`, using a `CNAME` record for `issues` at the
  slicer.org DNS provider (Namecheap) pointing to the site's `*.netlify.app` address.
- HTTPS certificate issued automatically by Netlify.

Check it with:

```
curl -sI https://issues.slicer.org/123
```
