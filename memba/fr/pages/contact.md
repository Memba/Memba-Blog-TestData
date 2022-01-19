---
category: Miscellaneous
description: Un formulaire pour nous contacter.
icon: user_telephone
keywords: Memba, Kidoju, logiciel, éducation, enseigner, apprendre, professeur, étudiant, connaissance, exercice, test, quiz, blog, article, documentation
language: fr
title: Nous contacter
uuid: 9aa49c0f-a12d-43d0-917c-ee76225bee7a
author: jlchereau
author_url: https://github.com/jlchereau
avatar_url: https://avatars.githubusercontent.com/u/2556751?v=3
edit_url: https://github.com/Memba/Memba-Blog-TestData/blob/master/memba/fr/pages/contact.md
site_url: http://localhost:3000/fr/contact
creation_date: 2016-04-12T08:51:27Z
---
<div id="alert" class="row" style="display:none;">
    <div class="col-sm-12">
        <div class="alert alert-success" role="alert">
            Merci pour avoir complété ce formulaire.
        </div>
    </div>    
</div>
<div class="row">
    <div class="col-sm-8">
        <form name="contact" action="/form" method="post" class="k-widget k-form">
            <div class="k-form-field">
                <label for="firstName" class="k-label k-form-label">Prénom&nbsp;: </label>
                <span class="k-input k-textbox k-rounded">
                    <input id="firstName" name="FirstName" type="text" class="k-input-inner" style="width: 100%" required>
                </span>
            </div>
            <div class="k-form-field">
                <label for="lastName" class="k-label k-form-label">Nom&nbsp;: </label>
                <span class="k-input k-textbox k-rounded">
                    <input id="lastName" name="LastName" type="text" class="k-input-inner" style="width: 100%" required>
                </span>
            </div>
            <div class="k-form-field">
                <label for="organization" class="k-label k-form-label">Organisation&nbsp;: </label>
                <span class="k-input k-textbox k-rounded">
                    <input id="organization" name="Organization" type="text" class="k-input-inner" style="width: 100%">
                </span>
            </div>
            <div class="k-form-field">
                <label for="role" class="k-label k-form-label">Fonction&nbsp;: </label>
                <span class="k-input k-textbox k-rounded">
                    <input id="role" name="Role" type="text" class="k-input-inner" style="width: 100%">
                </span>
            </div>
            <div class="k-form-field">
                <label for="email" class="k-label k-form-label">E-mail&nbsp;: </label>
                <span class="k-input k-textbox k-rounded">
                    <input id="email" name="Email" type="email" class="k-input-inner" style="width: 100%" required>
                </span>
            </div>
            <div class="k-form-field">
                <label for="phone" class="k-label k-form-label">Téléphone&nbsp;: </label>
                <span class="k-input k-textbox k-rounded">
                    <input id="phone" name="Phone" type="text" class="k-input-inner" style="width: 100%">
                </span>
            </div>
            <div class="k-form-field">
                <label for="message" class="k-label k-form-label">Message&nbsp;: </label>
                <span class="k-input k-textarea k-rounded k-resize-vertical">
                    <textarea id="message" name="Message" class="k-input-inner" style="width: 100%; height: 150px; resize: vertical" required></textarea>
                </span>
            </div>
            <div class="k-form-buttons">
                <input type="submit" value="Soumettre" class="k-button k-primary">
            </div>
        </form>
    </div>
    <div class="col-sm-4">
        <p><strong>Ou écrivez-nous à:</strong></p>
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
