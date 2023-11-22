```markdown
# Copy to Clipboard Functionality

This repository demonstrates how to implement copy-to-clipboard functionality in a web application using JavaScript.

## Usage

1. Include the HTML input element for copying:

```html
<input type="text" value="<?php the_permalink(); ?>" id="myInput" class="clipboard_input_careers_field">
```

Replace `<?php the_permalink(); ?>` with the dynamic content you want to copy.

2. Include the JavaScript functions for copying and tooltip display:

```html
<script>
function myFunction() {
  var copyText = document.getElementById("myInput");
  copyText.select();
  copyText.setSelectionRange(0, 99999);
  navigator.clipboard.writeText(copyText.value);
  
  var tooltip = document.getElementById("myTooltip");
  tooltip.innerHTML = "Copied: " + copyText.value;
}

function outFunc() {
  var tooltip = document.getElementById("myTooltip");
  tooltip.innerHTML = "Copied";
}
</script>
```

3. Add the tooltip container and trigger element:

```html
<div class="__tooltip">
    <span onclick="myFunction()" onmouseout="outFunc()">
        <span class="tooltiptext" id="myTooltip">Copy to clipboard</span>
        <img src="<?php bloginfo('template_directory');?>/assets/images/share_icon.png" alt="">
    </span>
</div>
```

Replace `<?php bloginfo('template_directory');?>/assets/images/share_icon.png` with the correct path to your image.

4. Customize the styles for the tooltip as needed.
