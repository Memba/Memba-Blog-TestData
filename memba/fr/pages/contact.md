---
category: Miscellaneous
description: Un formulaire pour nous contacter.
icon: user_telephone
keywords: Memba, Kidoju, logiciel, éducation, enseigner, apprendre, professeur, étudiant, connaissance, exercice, test, quiz, blog, article, documentation
language: en
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
        <form name="contact" action="/form" method="post">
            <div class="form-group">
                <label for="firstName">Prénom&nbsp;: </label>
                <input id="firstName" name="FirstName" type="text" class="k-textbox" style="width: 100%" required>
            </div>
            <div class="form-group">
                <label for="lastName">Nom&nbsp;: </label>
                <input id="lastName" name="LastName" type="text" class="k-textbox" style="width: 100%" required>
            </div>
            <div class="form-group">
                <label for="organization">Organisation&nbsp;: </label>
                <input id="organization" name="Organization" type="text" class="k-textbox" style="width: 100%">
            </div>
            <div class="form-group">
                <label for="role">Fonction&nbsp;: </label>
                <input id="role" name="Role" type="text" class="k-textbox" style="width: 100%">
            </div>
            <div class="form-group">
                <label for="email">E-mail&nbsp;: </label>
                <input id="email" name="Email" type="email" class="k-textbox" style="width: 100%" required>
            </div>
            <div class="form-group">
                <label for="phone">Téléphone&nbsp;: </label>
                <input id="phone" name="Phone" type="text" class="k-textbox" style="width: 100%">
            </div>
            <div class="form-group">
                <label for="message">Message&nbsp;: </label>
                <textarea id="message" name="Message" class="k-textbox" style="width: 100%; height: 150px; resize: vertical" required></textarea>
            </div>
            <div class="form-group">
                <input type="submit" value="Soumettre" class="k-button k-primary pull-right">
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
