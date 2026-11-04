<script setup>
const products = [
  {
    id: 'sound-licht',
    number: '01',
    category: 'Sound & Licht',
    title: 'Musikanlage & Licht',
    description:
      'Der richtige Sound und das passende Licht für Geburtstage, Hochzeiten, Gartenpartys und Vereinsfeiern.',
    image: 'c03e19c6-617a-4707-8947-8b807230dfd7.avif',
    imageAlt: 'Musikanlage mit Mikrofonen und Lichtanlage',
    price: '90',
    priceNote: 'inkl. Mikrofone',
    details: ['Leistungsstarke Musikbox & Mikrofone', 'Lichtanlage für Partybeleuchtung', 'Einfach zu bedienen'],
    extra: 'Einzelmiete der Geräte auf Anfrage.',
  },
  {
    id: 'bierzapfanlage',
    number: '02',
    category: 'Getränke',
    title: 'Bierzapfanlage',
    description:
      'Frisch gezapftes Bier für Geburtstage, Gartenpartys, Vereinsfeiern und andere Veranstaltungen.',
    image: '5d1c179f-d841-48cb-a107-53210b78db62.avif',
    imageAlt: 'Bierzapfanlage mit Zapfhähnen und Zubehör',
    price: '50',
    priceNote: 'pro Tag',
    details: ['Für private Feiern & Events', 'Abholung in 49577 Ankum'],
  },
  {
    id: 'kickautomat',
    number: '03',
    category: 'Eventautomat',
    title: 'Kickautomat',
    subtitle: 'Super Kick',
    description:
      'Schussstärke messen, Score vergleichen und gemeinsam mit Freunden, Familie oder Kollegen mitfiebern.',
    image: '4bf79efe-0fc0-4486-91cf-3f8cd943de99.avif',
    imageAlt: 'Kickautomat Super Kick für Kinder und Erwachsene',
    price: '50',
    priceNote: 'Mo–Do pro Tag',
    weekend: 'Fr 120 € · Sa 120 € · So 120 € · Fr–So 250 €',
    details: ['Für Kinder & Erwachsene', 'Abholung nach Absprache', 'Lieferung gegen Aufpreis möglich'],
  },
  {
    id: 'boxautomat',
    number: '04',
    category: 'Eventautomat',
    title: 'Boxautomat',
    description:
      'Einmal zuschlagen und den eigenen Score herausfordern – ein Publikumsmagnet für kleine Wettkämpfe.',
    image: 'd8700d8b-572b-4295-a71e-b083fdc428a7.avif',
    imageAlt: 'Boxautomat als Unterhaltung für deine Veranstaltung',
    price: '50',
    priceNote: 'Mo–Do pro Tag',
    weekend: 'Fr 100 € · Sa 100 € · So 100 € · Fr–So 250 €',
    details: ['Für Kinder & Erwachsene', 'Abholung nach Absprache', 'Lieferung gegen Aufpreis möglich'],
  },
  {
    id: 'anhaenger',
    number: '05',
    category: 'Transport',
    title: 'Anhänger mit Hochplane',
    description:
      'Geräumig und wettergeschützt – praktisch für Umzüge, Möbeltransporte, größere Einkäufe und Events.',
    image: '5b586ebe-fa63-48dd-b61b-69feeba5dfd5.avif',
    imageAlt: 'Geräumiger Anhänger mit Hochplane',
    price: '30',
    priceNote: 'pro Tag',
    details: ['Länge 306 cm', 'Breite 153 cm', 'Höhe 170 cm'],
  },
  {
    id: 'hau-den-lukas',
    number: '06',
    category: 'Eventautomat',
    title: 'Hau den Lukas',
    description:
      'Der Klassiker für den großen Auftritt: Wer erzielt den höchsten Score? Spaß und Spannung für Groß und Klein.',
    image: '5f3ef2d7-55ea-4199-ae2c-88d3b6c009c3.avif',
    imageAlt: 'Hau den Lukas Automat für Feste und Veranstaltungen',
    price: '50',
    priceNote: 'Mo–Do pro Tag',
    weekend: 'Fr 100 € · Sa 100 € · So 100 € · Fr–So 250 €',
    details: ['Für Geburtstage, Hochzeiten & Vereinsfeste', 'Weitere Automaten zubuchbar', 'Mengenrabatt bei mehreren Automaten'],
  },
]

const imageUrl = (file) => `${import.meta.env.BASE_URL}Product-Images/${file}`
const contactUrl = 'https://www.kleinanzeigen.de/s-bestandsliste.html?userId=145416712'
</script>

<template>
  <header class="site-header">
    <a class="brand" href="#start" aria-label="KD-Eventservice – zur Startseite">
      <span class="brand-mark">KD<span>.</span></span>
      <span class="brand-name">EVENT<span>SERVICE</span></span>
    </a>
    <nav aria-label="Hauptnavigation">
      <a href="#angebote">Mietangebote</a>
      <a href="#ablauf">So funktioniert’s</a>
      <a class="nav-cta" :href="contactUrl" target="_blank" rel="noreferrer">Anfrage stellen <span aria-hidden="true">↗</span></a>
    </nav>
  </header>

  <main>
    <section id="start" class="hero">
      <div class="hero-content">
        <p class="eyebrow"><span class="status-dot"></span> EVENTVERLEIH AUS ANKUM</p>
        <h1>Dein Event.<br />Dein <span>Highlight.</span></h1>
        <p class="hero-copy">
          Von sattem Sound bis zum Kick am Automaten – miete unkompliziert das Extra, das deine Feier unvergesslich macht.
        </p>
        <div class="hero-actions">
          <a class="button button-primary" href="#angebote">Angebote entdecken <span aria-hidden="true">↓</span></a>
          <a class="text-link" :href="contactUrl" target="_blank" rel="noreferrer">Jetzt unverbindlich anfragen <span aria-hidden="true">↗</span></a>
        </div>
        <div class="hero-meta">
          <span><span class="meta-icon">⌖</span> 49577 Ankum</span>
          <span class="meta-divider"></span>
          <span>Abholung oder Lieferung nach Absprache</span>
        </div>
      </div>
      <div class="hero-art" aria-hidden="true">
        <img
          class="hero-photo"
          :src="imageUrl('0294326f-6b58-4165-a352-08ef9a07de8f.avif')"
          alt=""
        />
        <span class="hero-photo-caption">KD-SERVICE <span>·</span> EVENTVERLEIH IN ANKUM</span>
      </div>
      <div class="hero-bottom"><span>GEBURTSTAG · HOCHZEIT · FIRMENFEIER · MEHR</span><span>SCROLLEN & ENTDECKEN ↓</span></div>
    </section>

    <section id="angebote" class="offers section-wrap">
      <div class="section-heading">
        <div>
          <p class="eyebrow">MACH DEIN EVENT BESONDERS</p>
          <h2>Das kannst du <span>mieten.</span></h2>
        </div>
        <p class="section-intro">Für kleine Runden und große Feiern. Such dir dein Highlight aus – den Rest besprechen wir persönlich.</p>
      </div>

      <div class="product-grid">
        <article
          v-for="product in products"
          :key="product.id"
          class="product-card"
        >
          <div class="product-photo">
            <img :src="imageUrl(product.image)" :alt="product.imageAlt" loading="lazy" />
            <span class="product-number">{{ product.number }}</span>
            <span class="product-category">{{ product.category }}</span>
          </div>
          <div class="product-content">
            <div class="product-title-row">
              <div>
                <h3>{{ product.title }}</h3>
                <p v-if="product.subtitle" class="product-subtitle">{{ product.subtitle }}</p>
              </div>
              <div class="price"><strong>{{ product.price }} €</strong><span>{{ product.priceNote }}</span></div>
            </div>
            <p class="product-description">{{ product.description }}</p>
            <ul class="product-details">
              <li v-for="detail in product.details" :key="detail"><span aria-hidden="true">✓</span>{{ detail }}</li>
            </ul>
            <p v-if="product.weekend" class="weekend-prices">{{ product.weekend }}</p>
            <p v-if="product.extra" class="product-extra">{{ product.extra }}</p>
            <a class="product-link" :href="contactUrl" target="_blank" rel="noreferrer">
              Verfügbarkeit anfragen <span aria-hidden="true">↗</span>
            </a>
          </div>
        </article>
      </div>
      <p class="offer-note">Automatenpreise gelten pro Tag, sofern nicht anders angegeben. Veranstaltungstechnik auch einzeln mietbar – Einzelpreise auf Anfrage.</p>
    </section>

    <section class="occasion">
      <div class="occasion-copy">
        <p class="eyebrow">VON DER IDEE BIS ZUM EVENT</p>
        <h2>Gute Feiern<br />bleiben <span>im Kopf.</span></h2>
      </div>
      <div class="occasion-content">
        <p>Geburtstag, Hochzeit, JGA, Gartenparty, Schützenfest oder Firmenfeier – mit dem passenden Equipment wird aus einem schönen Tag ein echtes Erlebnis.</p>
        <div class="occasion-tags">
          <span>Geburtstage</span><span>Hochzeiten</span><span>JGA</span><span>Firmenfeiern</span><span>Vereinsfeste</span><span>… und mehr</span>
        </div>
      </div>
      <span class="occasion-spark" aria-hidden="true">✳</span>
    </section>

    <section id="ablauf" class="how section-wrap">
      <div class="section-heading">
        <div><p class="eyebrow">GANZ OHNE KOMPLIZIERT</p><h2>In drei Schritten<br />zum <span>Highlight.</span></h2></div>
      </div>
      <div class="steps">
        <article class="step"><span class="step-number">01</span><h3>Wunschartikel wählen</h3><p>Entdecke das passende Extra für deine Feier – einzelne Artikel oder gleich mehrere Automaten.</p></article>
        <article class="step"><span class="step-number">02</span><h3>Termin anfragen</h3><p>Schreib uns über Kleinanzeigen mit deinem Datum und was du mieten möchtest.</p></article>
        <article class="step"><span class="step-number">03</span><h3>Feier genießen</h3><p>Abholung in Ankum oder Lieferung nach Absprache und Entfernung – dann kann gefeiert werden.</p></article>
      </div>
    </section>

    <section class="contact">
      <div class="contact-copy">
        <p class="eyebrow">DEIN TERMIN WARTET SCHON</p>
        <h2>Bereit für<br />dein <span>Highlight?</span></h2>
        <p>Frag deinen Wunschtermin ganz unverbindlich an. Wir freuen uns auf deine Nachricht!</p>
        <a class="button button-dark" :href="contactUrl" target="_blank" rel="noreferrer">Nachricht über Kleinanzeigen <span aria-hidden="true">↗</span></a>
      </div>
      <div class="contact-aside">
        <span class="contact-star" aria-hidden="true">✳</span>
        <p>DEIN EVENTVERLEIH<br /><strong>IN ANKUM & UMGEBUNG</strong></p>
        <span class="contact-pin">⌖ &nbsp;49577 Ankum</span>
      </div>
    </section>
  </main>

  <footer class="site-footer">
    <a class="brand footer-brand" href="#start"><span class="brand-mark">KD<span>.</span></span><span class="brand-name">EVENT<span>SERVICE</span></span></a>
    <p>Eventverleih für unvergessliche Feiern.</p>
    <a href="#start">Zurück nach oben ↑</a>
    <span class="copyright">© {{ new Date().getFullYear() }} KD-Eventservice</span>
  </footer>
</template>
