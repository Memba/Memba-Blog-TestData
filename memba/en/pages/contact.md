---
category: Miscellaneous
description: A contact form to reach us.
icon: user_telephone
keywords: Memba, Kidoju, software, education, teach, learn, teacher, student, knowledge, test, quiz, blog, article, documentation
language: en
title: Contact Us
uuid: daac815d-298b-406b-a707-0110a1c2685f
author: jlchereau
author_url: https://github.com/jlchereau
avatar_url: https://avatars.githubusercontent.com/u/2556751?v=3
edit_url: https://github.com/Memba/Memba-Blog-TestData/blob/master/memba/en/pages/contact.md
site_url: http://localhost:3000/en/contact
creation_date: 2016-04-12T08:56:29Z
---
<div id="alert" class="row" style="display:none;">
    <div class="col-sm-12">
        <div class="alert alert-success" role="alert">
            Thank you for completing this form.
        </div>
    </div>    
</div>
<div class="row">
    <div class="col-sm-8">
        <form name="contact" action="/form" method="post" class="k-widget k-form">
            <div class="k-form-field">
                <label for="firstName" class="k-label k-form-label">First Name: </label>
                    <input id="firstName" name="FirstName" type="text" class="k-input-inner" style="width: 100%" required>
                </span>
            </div>
            <div class="k-form-field">
                <label for="lastName" class="k-label k-form-label">Last Name: </label>
                <span class="k-input k-textbox k-rounded">
                    <input id="lastName" name="LastName" type="text" class="k-input-inner" style="width: 100%" required>
                </span>
            </div>
            <div class="k-form-field">
                <label for="organization" class="k-label k-form-label">Organisation: </label>
                <span class="k-input k-textbox k-rounded">
                    <input id="organization" name="Organization" type="text" class="k-input-inner" style="width: 100%">
                </span>
            </div>
            <div class="k-form-field">
                <label for="role" class="k-label k-form-label">Role: </label>
                <span class="k-input k-textbox k-rounded">
                    <input id="role" name="Role" type="text" class="k-input-inner" style="width: 100%">
                </span>
            </div>
            <div class="k-form-field">
                <label for="email" class="k-label k-form-label">E-mail: </label>
                <span class="k-input k-textbox k-rounded">
                    <input id="email" name="Email" type="email" class="k-input-inner" style="width: 100%" required>
                </span>
            </div>
            <div class="k-form-field">
                <label for="phone" class="k-label k-form-label">Phone: </label>
                <span class="k-input k-textbox k-rounded">
                    <input id="phone" name="Phone" type="text" class="k-input-inner" style="width: 100%">
                </span>
            </div>
            <div class="k-form-field">
                <label for="message" class="k-label k-form-label">Message: </label>
                <span class="k-input k-textarea k-rounded k-resize-vertical">
                    <textarea id="message" name="Message" class="k-input-inner k-overflow-auto" style="width: 100%; height: 150px; resize: vertical" required></textarea>
                </span>
            </div>
            <div class="k-form-buttons">
                <input type="submit" value="Submit" class="k-button k-button-md k-rounded k-input-button k-button-solid k-button-solid-primary k-float-right">
            </div>
        </form>
    </div>
    <div class="col-sm-4">
        <p><strong>Or write us at:</strong></p>
        <address>
            Memba Sarl<br/>
            20 avenue Pasteur<br/>
            L-2310 Luxembourg
        </address>
    </div>
</div>

<script>
;(function (window, $, undefined) {
    $(function () {
        var form = $('form[name="contact"]');
        if ($.fn.kendoValidator) {
            var validator = form.kendoValidator().data('kendoValidator');
            form.submit(function (e) {
                if (!validator.validate()) {
                    e.preventDefault();
                }
            });
        }
        var hash = window.location.hash.substr(1).split(/[&=]/);
        var length = hash.length;
        if (length === 2 && hash[0] === 'success' && hash[1] === 'true') {
            $('#alert').show();
        } else if (Math.floor(length / 2) === length / 2) {
            for (var i = 0; i < length / 2; i++) {
                $('#' + hash[2 * i].toLowerCase()).val(hash[2 * i + 1]);
            }
        }
        setTimeout(function () {
            var a = Math.floor(100 * Math.random());
            var b = Math.floor(100 * Math.random());
            form.append('<input name="__a" type="hidden" value="' + a + '+' + b + '">');
            form.append('<input name="__b" type="hidden" value="' + (a + b) + '">');
        }, 15 * 1000);
    });
}(this, jQuery));
</script>
