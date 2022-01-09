---
title: "Contact"
permalink: "/contact"
---

<form action="https://formspree.io/{{site.email}}" method="POST">    
<p class="mb-4">Please send your message to {{site.name}}. I will reply as soon as possible!</p>
<div class="form-group row">
<div class="col-md-6">
<input class="form-control" type="text" name="name" placeholder="First and Last Name..." required>
</div>
<div class="col-md-6">
<input class="form-control" type="email" name="_replyto" placeholder="E-mail..." required>
</div>
</div>
<textarea rows="8" class="form-control mb-3" name="message" placeholder="Message..." required></textarea>    
<input class="btn btn-default btn-block" type="submit" value="Send">
</form>