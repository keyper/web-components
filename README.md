# keyper Web Componenets

## Concepts

Read more about the concept of Web Components [here](https://developer.mozilla.org/de/docs/Web/Web_Components).

keyper Web components are custom elements and use the shadow DOM.

## Getting started

First you have to incluce the web component into your html page.
To do so, load the component from `URL TO BE DEFINED`.

```
<html>
  <head>
    ...
    <script type="text/javascript" src="URL">
  </head>
  <body>
  ...
  </body>
</html>
```

You can also place the script at in the body of your application. However, ensure that the script is loaded before initializing the custom element.

### Including the custom element

The name of the custom element is `keyper-web`. For information about including it, have a look at the following snippet.

```
<html>
  <head>
    ...
    <script type="text/javascript" src="URL">
  </head>
  <body>
    <keyper-web
      attribute="text"
      attributeTwo="text2"
      ...
    ></keyper-web>
  </body>
</html>
```

### Attributes

| Name             | Type              | Value                                                                           |
| ---------------- | ----------------- | ------------------------------------------------------------------------------- |
| appSecret        | string (required) | App secret obtained by keyper Business Webapp, e.g. `100001_a1b2c3`             |
| ssoToken         | string (required) | Token of the signed in user in your SSO (e.g. JWT)                              |
| environment      | string (optional) | develop \| staging \| sandbox \| production (default)                           |
| language         | string (optional) | Language of the user (defaults to `navigator.language` or `de`)                 |
| verificationType | string (optional) | verification type of the offer URL, e.g. `offers_gift_existing_user`            |
| verificationCode | string (optional) | verification code of the offer URL, e.g. `AB11C3DE-4567-8F90-12AB-AB34C56D789E` |
| component        | string (optional) | component that should be loaded; can be "notification" \| "container" (default) |


### Offer handling

When somebody send a ticket offer, the recipient receives an email with the link to the offer. This URL has to link to your site and you have to handle forwarding information to the web components. To make this possible, three steps are necessary:

1. Configure your custom offer URL in the keyper business dashboard (settings -> applications -> ticketing widgets).
2. When a customer receives the ticket, you have to ensure that the link is handled correctly and log in the user. We provide an api call to get the user information of the recipient.
3. Forward the verificationType and verificationCode to the web compoents.

## Support

If you have any futher questions don´t hesistate to [contact us](mailto:developers@keyper.io?subject=keyper%20web%20components).
