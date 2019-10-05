---
title: Newsletter
weight: 50
hidden: true
---

<!-- Tiny newletter integration -->
<section class="newsletter">
    <form
        action="https://tinyletter.com/devdash"
        method="post"
        target="popupwindow"
        onsubmit="window.open('https://tinyletter.com/devdash', 'popupwindow', 'scrollbars=yes,width=800,height=600');return true"
        >
        <p>
            <label for="tlemail">Last releases and important news in your mailbox. No spam.</label>
        </p>
        <p>
            <input type="text" name="email" placeholder="My email address" id="tlemail" />
        </p>
        <input type="hidden" value="1" name="embed"/>
        <input type="submit" value="Subscribe" />
    </form>
</section>
