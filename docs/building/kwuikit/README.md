# Building Applications - KW UI Kit

### What is the KW UI Kit?

The [KW UI Kit](https://github.com/KWRI/kwuikit) is a front-end toolkit, similar to [Bootstrap](https://getbootstrap.com/), for building responsive, consistent applications. It provides a series of primitive React components that can be pieced together to create complex user interfaces.

---

### Supporting Articles

1.  [Guiding Principles](principles.md)
1.  [Usage Documentation](http://kwuikit.s3-website-us-east-1.amazonaws.com/)
1.  [Contributing](contributing.md)
1.  [Code Guidelines](guidelines.md)

---

If you're installing the KW UI Kit into an application **outside of the console**, you will need to include the stylesheet for the kit.

```js
import 'kwuikit/lib/kwuikit.css'
```

> This is only necessary for projects outside of this repository. You should not include the above import statement anywhere within the console
