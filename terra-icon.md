# Accessibility Guide for Terra Icon

## Why is icon accessibility important?

Accessibility of icons is important because icons are ubiquitous. They can convey visual meaning or be used as a decorative or supportive element in a UI design and are an essential tool for creating intuitive user experiences that are appropriate for all languages. However, if implemented improperly or without alternative content, they are **not** understood natively by everyone.

Since icons are images, they are not inherently accessible to all users, especially those with significantly impaired vision or blindness. Therefore, interface icons **must** have alternative content.

Screen readers convey alternative content to users who have difficulty interpreting icons. Speech input devices also use alternative content to target specific icons.

It is common for interfaces to use multiples of the same icon on a screen. Development and content teams must consider this use case to ensure all users can predictably understand the icon’s purpose.

Users expect identical icons to perform the same function. Similarly, screen reader users expect their software to identify identical icons consistently. Therefore, failure to provide consistent identification (visual or alternative content) can cause problems for all users.

In addition, people who use only their voice to interact with technology also rely upon consistent alternative content behind the icons to ensure they can interact with controls.

## Accessibility Considerations

### Meaningful Use of Icons

Icons that convey information **must** have alternative text in code to ensure that assistive technologies pass the icon’s meaning to the user.

**[IMAGE OR CODE EXAMPLE]**

In this example, the plus (+) icon is meaningful.

Although the icon is visually related to “Clinical Note,” no text supports its function to “add” something. Therefore, the icon’s code must include `alt=”Add”` to adequately convey this to a screen reader user. The screen reader would read the icon’s alternative text, followed by the button’s text label. In all, the user would hear, **”Add Clinical Note.”**

#### Considerations for Meaningful Icons Used Within Components

This example shows an icon used within a button. A button element receives visual focus when navigating with a keyboard. When a screen reader announces this element’s focus, it reads the icon’s alternative text, the button’s label, and its role.

In this example, the screen reader would say, **”Add Clinical Note. Button.”** The user would also expect to hear instructions for interacting with the button (e.g., pressing the `Enter` key or `Space`).

### Decorative Use of Icons

In decorative use, an icon provides no additional information or context. Meaning that, without the icon, the user would still know the meaning and purpose of the button.

**[IMAGE OR CODE EXAMPLE]**

The plus (+) icon, in this case, is purely decorative. It supplements the button’s text label, which informs the user of the element’s purpose.

Since the icon is decorative, its code must feature `alt=”“` to ensure screen readers do not announce the icon’s presence. For example, if this icon had `alt=”Add”` in its code, a screen reader user would hear something like, **”Add Add Clinical Note.”** This is not only redundant but adds cognitive friction and possible confusion.

### Code Considerations

- Appropriately code each icon as being meaningful or decorative. Ensure each meaningful icon has alternative text provided by the content creator.
- Do not overwrite theme colors unless UX provides custom colors. All custom colors must pass WCAG 2.1 color accessibility requirements.

### Content Considerations

- Specify **every** icon instance as meaningful or decorative. Provide developers with clear and concise alternative text for meaningful icons that accurately reflect the icon’s meaning or purpose.
- While some icons are ubiquitous and generally intuitive (e.g., printer icon), it is best to use words with icons.
- Icon meaning must be consistent throughout the product. For example, a plus (+) icon must always represent “add” functionality. In addition, if multiples of the same icon are in [repeated controls on the same page](https://adrianroselli.com/2019/06/group-labels-do-not-guarantee-uniquity.html), the combination of alternative text and text label must be [unique](https://fae.disability.illinois.edu/rulesets/CONTROL_10/) (e.g., “Add Blood Pressure” and “Add Temperature”).
- Colors for icons are predefined in each of Terra’s visual themes. When icon colors require customization, they must meet WCAG Success Criteria for [1.4.3 Contrast (Minimum) (Level AA)](https://www.w3.org/WAI/WCAG21/Understanding/contrast-minimum.html), which is a 3:1 contrast ratio. Ensure icon colors have sufficient contrast against background colors with the [Colour Contrast Analyzer](https://www.tpgi.com/color-contrast-checker/).
- Use color to enhance, not convey, icon meaning. For example, changing an icon’s color from green to red to indicate a status change would fail accessibility requirements if no words or symbols were associated with the icon.

#### Additional Writing Resources and Content Strategies

::TO DO - Or is this the same for all components?::

## Usability Expectations

### Interaction Details

::TO DO::

### Keyboard Navigation

::TO DO - Probably not needed for icon?::

## Concerns and Hazards

::TO DO::

## Support and Compliance

Terra is committed to ensuring its components provide maximum possible accessibility. However, using Terra components will not automatically make your product accessible. At most, consuming this component accounts for 33% of a product’s accessibility — the rest is up to development teams to implement.

This component has **[known / no known]** accessibility failures. If you find accessibility bugs or gaps, please [report these issues on Github](https://github.com/cerner/terra-core/issues/new/choose).

### Known Issues

<!-- TO DO - If known issues, list here -->

## Support Compliance for Terra Icon

<!-- The style of this section in pills and icon are markedly different. Does that matter? -->

- **Functionality** - Terra provides an icon component that correctly sets alternative text values based on whether the icon has been deemed meaningful or decorative.
- **Color** - Terra provides theme colors that meet WCAG Success Criteria for [1.4.3 Contrast (Minimum) (Level AA)](https://www.w3.org/WAI/WCAG21/Understanding/contrast-minimum.html).
- **Assistive Technologies** - <!-- TO DO -->

*For more information about Accessibility Support with Terra — go to [Component Standards: Accessibility (A11y)](https://engineering.cerner.com/terra-ui/about/terra-ui/component-standards#accessibility-a11y).*
