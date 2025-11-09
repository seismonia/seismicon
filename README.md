## Icons preview and comments
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="pointer-cone-down.svg">
  <img src="pointer-cone-down.svg" alt="Pointer Icon" width="24" height="24" style="background: #f1f1f1; border-radius: 4px;">
</picture>
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="station-seismic.svg">
  <img src="station-seismic.svg" alt="Seismic Station" width="48" height="48" style="background: #f1f1f1; border-radius: 8px;">
</picture>

## Simplest example ![pointer-cone-down.svg](pointer-cone-down.svg) (`pointer-cone-down.svg`) content:
```xml
<svg
  xmlns="http://www.w3.org/2000/svg"
  width="24"
  height="24"
  viewBox="0 0 24 24"
  fill="none"
  stroke="currentColor"
  stroke-width="2"
  stroke-linecap="round"
  stroke-linejoin="round"
>
   <path 
      style="fill:currentColor"
      d="m 3,8.75 c 0,0 5.55,5 9,5 3.45,0 9,-5 9,-5 L 12,22 Z" />
   <path
      style="stroke-width:2.2"
      d="M 2.5,7 A 9.5,5 0 0 1 12,2 9.5,5 0 0 1 21.5,7 9.5,5 0 0 1 12,12 9.5,5 0 0 1 2.5,7" />
</svg>
```

SVG attributes used (default section):
+ `width="24" & height="24" & viewBox="0 0 24 24"` - simple (small) icon
+ `fill="none"` - transparent
+ `stroke="currentColor"` - adopts parent element color
+ `stroke-width="2"` - base line weight
+ `stroke-linecap="round"` - rounded line ends
+  `stroke-linejoin="round"` - rounded corners

Path specific attributes:
+ `style="fill:currentColor"` - themed fill instead of transperent
+ `style="stroke-width:2.2"` - thicker line to avoid imperfections

## 🎨 Icon Design & Optimization Workflow
The design language was partially inspired by [Lucide Design Principles](https://lucide.dev/guide/design/icon-design-guide)

Icons are in [SVG](https://en.wikipedia.org/wiki/SVG) format, most essential basic one (see example above).

### Design Phase (Inkscape, CorelDraw, etc.)
1. Create icon in the software you familiar but stick to the following:
   - 24×24px or 48×48px artboards
   - 2px stroke width (`stroke-width="2"`)
   - `currentColor` for fills/strokes (makes icons themable)

### Optimization Phase (Manual Cleanup)
Vector graphic software usually adds substantial metadata, attributes, groupping and so on, so to keep the icon essense pure - I prefer to manually optimize it, validate and only then commit via pull-request so this way the main branch stays as clean as possible and can be used as a git submodule in another project. 

Optimization Steps example workflow:
1. Open in VS Code/Codium and switch between text/XML mode and image preview
2. Remove software metadata, attributes, structures...
3. Minify actually used attributes (keep defaults as whole svg attributes)
4. Verify rendering in image preview
5. Validate and test in target applications (web, print, etc.)

## Contributing
Icon contributions are welcomed!

**Direct repository access workflow (Seismonia member):**
1. Create a feature branch from main named: `dev-your-icon-set-name`
    + Examples: dev-natural, dev-industrial
2. Add your SVG icons in the appropriate category folder(s)
3. Submit a Pull Request from your dev-\* branch to main
4. Review -> optimization -> merge once icons are clean .svg

**Fork & PR workflow (any GitHub user/org):**
1. Fork this repository to your GitHub account
2. Create a feature branch in your fork: `dev-your-icon-set-name`
3. Add your SVG icons following design guidelines mentioned above
4. Submit a Pull Request from your fork to Seismonia's main branch

### Branch Protection
- main branch: Protected - requires PR review and optimization pass
- dev-\* branches: Open for development and collaboration