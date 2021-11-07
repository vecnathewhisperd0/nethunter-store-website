---
layout: default
permalink: /

---

{% assign strings = site.data.strings.index %}

<h2>{{strings.title}}</h2>

{{strings.introduction}}

<div class="download-and-screenshot">
    <div class="download">
        <div class="button">
            <a class="material-button" href=" https://store.nethunter.com/NetHunterStore.apk">{{ strings.download_fdroid }}</a>
        </div>
        <div class="gpg">
            <a href=" https://store.nethunter.com/NetHunterStore.apk.asc">{{ strings.gpg_signature }}</a>
        </div>
        <div class="qr">
            <img src="{{ site.baseurl }}/assets/download-nethunter-store-qr.png" />
        </div>
    </div>
    <div class="screenshot">
        <img
            src="{% asset phone-frame.png %}" alt="{{ strings.screenshot }}"
            style="background: url('{{ site.baseurl }}/{% fdroid_screenshot %}') center center no-repeat; background-size: 78% auto" />
    </div>
</div>

<script src="{% asset donate.js %}"></script>
