---
title: HTMLLinkElement
slug: Web/API/HTMLLinkElement
---

{{ APIRef("HTML DOM") }}

The **`HTMLLinkElement`** interface represents reference information for external resources and the relationship of those resources to a document and vice-versa. This object inherits all of the properties and methods of the {{domxref("HTMLElement")}} interface.

{{InheritanceDiagram(600, 120)}}

## Properties

_Inherits properties from its parent, {{domxref("HTMLElement")}}, and {{domxref("LinkStyle")}}._

- {{domxref("HTMLLinkElement.as")}}

  - : Is a {{domxref("DOMString")}} representing the type of content being loaded by the HTML link.

- {{domxref("HTMLLinkElement.crossOrigin")}} {{experimental_inline}}
  - : Is a {{domxref("DOMString")}} that corresponds to the CORS setting for this link element. See [CORS settings attributes](/zh-CN/docs/HTML/CORS_settings_attributes) for details.
- {{domxref("HTMLLinkElement.disabled")}}
  - : Is a `Boolean` which represents whether the link is disabled; currently only used with style sheet links.
- {{domxref("HTMLLinkElement.href")}}
  - : Is a {{domxref("DOMString")}} representing the URI for the target resource.
- {{domxref("HTMLLinkElement.hreflang")}}
  - : Is a {{domxref("DOMString")}} representing the language code for the linked resource.
- {{domxref("HTMLLinkElement.media")}}
  - : Is a {{domxref("DOMString")}} representing a list of one or more media formats to which the resource applies.
- {{domxref("HTMLLinkElement.referrerPolicy")}} {{experimental_inline}}
  - : Is a {{domxref("DOMString")}} that reflects the [`referrerpolicy`](/zh-CN/docs/Web/HTML/Element/link#referrerpolicy) HTML attribute indicating which referrer to use.
- {{domxref("HTMLLinkElement.rel")}}
  - : Is a {{domxref("DOMString")}} representing the forward relationship of the linked resource from the document to the resource.
- {{domxref("HTMLLinkElement.relList")}} {{readonlyInline}}
  - : Is a {{domxref("DOMTokenList")}} that reflects the [`rel`](/zh-CN/docs/Web/HTML/Element/link#rel) HTML attribute, as a list of tokens.
- {{domxref("HTMLLinkElement.sizes")}} {{readonlyInline}}
  - : Is a {{domxref("DOMSettableTokenList")}} that reflects the [`sizes`](/zh-CN/docs/Web/HTML/Element/link#sizes) HTML attribute, as a list of tokens.
- {{domxref("LinkStyle.sheet")}} {{readonlyInline}}
  - : Returns the {{domxref("StyleSheet")}} object associated with the given element, or `null` if there is none.
- {{domxref("HTMLLinkElement.type")}}
  - : Is a {{domxref("DOMString")}} representing the MIME type of the linked resource.

### Obsolete properties

- {{domxref("HTMLLinkElement.charset")}} {{Deprecated_Inline}}
  - : Is a {{domxref("DOMString")}} representing the character encoding for the target resource.
- {{domxref("HTMLLinkElement.rev")}} {{Deprecated_Inline}}

  - : Is a {{domxref("DOMString")}} representing the reverse relationship of the linked resource from the resource to the document.

    > **备注：** Currently the W3C HTML 5.2 spec states that `rev` is no longer obsolete, whereas the WHATWG living standard still has it labeled obsolete. Until this discrepancy is resolved, you should still assume it is obsolete.

- {{domxref("HTMLLinkElement.target")}} {{Deprecated_Inline}}
  - : Is a {{domxref("DOMString")}} representing the name of the target frame to which the resource applies.

## Methods

_No specific method; inherits methods from its parent, {{domxref("HTMLElement")}}, and {{domxref("LinkStyle")}}._

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- The HTML element implementing this interface: {{HTMLElement("link")}}.
