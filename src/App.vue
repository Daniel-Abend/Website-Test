<script setup>
import { ref, watch } from 'vue'

const activeService = ref('event')

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
    link: 'https://www.kleinanzeigen.de/s-anzeige/musikanlage-mikrofone-lichtanlage-bierzapfanlage-mieten/3522664283-233-17095'
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
    link: 'https://www.kleinanzeigen.de/s-anzeige/musikanlage-mikrofone-lichtanlage-bierzapfanlage-mieten/3522664283-233-17095'
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
    link: 'https://www.kleinanzeigen.de/s-anzeige/kickautomat-zur-huepfburg-geburtstag-firmenfeier-hochzeit-jga/3522649840-233-17095'
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
    link: 'https://www.kleinanzeigen.de/s-anzeige/boxautomat-zu-vermieten-geburtstag-firmenfeier-hochzeit-jga/3522656963-233-17095'
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
    link: 'https://www.kleinanzeigen.de/s-anzeige/anhaenger-mit-plane-zu-vermieten-306-153-170-cm/3538327034-238-17095'
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
    link: 'https://www.kleinanzeigen.de/s-anzeige/hau-den-lukas-zur-huepfburg-geburtstag-firmenfeier-hochzeit-jga/3538322709-233-17095'
  }
]

const imageUrl = (file) => `${import.meta.env.BASE_URL}Product-Images/${file}`
const contactUrl = 'https://www.kleinanzeigen.de/s-bestandsliste.html?userId=145416712'
const cadContactUrl = 'https://www.kleinanzeigen.de/s-anzeige/cad-dienstleistung-technische-zeichnungen-3d-druck-dxf-step-stl/3538712058-298-17095'

watch(activeService, (service) => {
  document.title = service === 'cad'
    ? 'KD-Service | CAD-Konstruktion & 3D-Druck'
    : 'KD-Eventservice | Eventverleih'
  window.scrollTo({ top: 0, behavior: 'smooth' })
})
</script>

<template>
  <div class="site-shell" :class="{ 'cad-mode': activeService === 'cad' }">
    <header class="site-header">
    <div class="service-switch" role="group" aria-label="KD-Service Bereich auswählen">
      <button
        class="service-tab event-tab"
        :class="{ active: activeService === 'event' }"
        type="button"
        :aria-pressed="activeService === 'event'"
        @click="activeService = 'event'"
      >
        <span class="brand-mark">KD<span>.</span></span>
        <span class="brand-name">KD-SERVICE<span>KONSTRUKTION · EVENTVERLEIH</span></span>
      </button>
      <button
        class="service-tab cad-tab"
        :class="{ active: activeService === 'cad' }"
        type="button"
        :aria-pressed="activeService === 'cad'"
        @click="activeService = 'cad'"
      >
        <span class="brand-mark">KD<span>.</span></span>
        <span class="brand-name">KD-SERVICE<span>KONSTRUKTION · 3D-DRUCK</span></span>
      </button>
    </div>
    <nav aria-label="Hauptnavigation">
      <template v-if="activeService === 'event'">
        <a href="#angebote">Mietangebote</a>
        <a href="#ablauf">So funktioniert’s</a>
        <a class="nav-cta" :href="contactUrl" target="_blank" rel="noreferrer">Anfrage stellen <span aria-hidden="true">↗</span></a>
      </template>
      <template v-else>
        <a href="#cad-leistungen">Leistungen</a>
        <a href="#cad-ablauf">Projektablauf</a>
        <a class="nav-cta" :href="cadContactUrl" target="_blank" rel="noreferrer">Projekt anfragen <span aria-hidden="true">↗</span></a>
      </template>
    </nav>
    </header>

  <main v-if="activeService === 'event'">
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
            <a class="product-link" :href="product.link" target="_blank" rel="noreferrer">
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

  <main v-else class="cad-main">
    <section id="start" class="hero cad-hero">
      <div class="hero-content">
        <p class="eyebrow"><span class="status-dot"></span> KONSTRUKTION · CAD · 3D-DRUCK</p>
        <h1>Aus einer Idee<br />wird <span>ein Bauteil.</span></h1>
        <p class="hero-copy">
          Technische Zeichnungen, durchdachte CAD-Konstruktionen und 3D-Druck – persönlich, präzise und deutschlandweit digital.
        </p>
        <div class="hero-actions">
          <a class="button button-primary" href="#cad-leistungen">Leistungen entdecken <span aria-hidden="true">↓</span></a>
          <a class="text-link" :href="cadContactUrl" target="_blank" rel="noreferrer">Projekt unverbindlich besprechen <span aria-hidden="true">↗</span></a>
        </div>
        <div class="hero-meta">
          <span><span class="meta-icon">⌖</span> Deutschlandweit digital</span>
          <span class="meta-divider"></span>
          <span>Faire Festpreise nach Projektbesprechung</span>
        </div>
      </div>
      <div class="hero-art cad-hero-art">
        <img
          class="hero-photo"
          :src="imageUrl('76a791f3-9bc3-4c2b-9a71-4e0093cf7417.avif')"
          alt="KD-Service: technische Zeichnungen, CAD-Konstruktion und 3D-Druck"
        />
        <span class="hero-photo-caption">KD-SERVICE <span>·</span> KONSTRUKTION & 3D-DRUCK</span>
      </div>
      <div class="hero-bottom"><span>2D & 3D · TECHNISCHE ZEICHNUNGEN · 3D-DRUCK</span><span>VON DER SKIZZE ZUM MODELL</span></div>
    </section>

    <section id="cad-leistungen" class="offers section-wrap cad-offers">
      <div class="section-heading">
        <div>
          <p class="eyebrow">KONSTRUKTION, DIE WEITERDENKT</p>
          <h2>Von der Skizze bis<br />zum <span>fertigen Modell.</span></h2>
        </div>
        <p class="section-intro">Ob einzelne Anpassung oder vollständige Ausarbeitung – ich unterstütze Privatpersonen, Handwerk und Unternehmen bei ihrem Konstruktionsprojekt.</p>
      </div>
      <div class="cad-service-grid">
        <article class="cad-service-card">
          <span class="cad-service-number">01</span>
          <h3>CAD & Konstruktion</h3>
          <ul>
            <li>2D- und 3D-Konstruktionen</li>
            <li>Individuelle Bauteile und Sonderlösungen</li>
            <li>Stahlbau-, Blech- und Maschinenbaukonstruktionen</li>
            <li>Konstruktion von Dreh- und Frästeilen</li>
            <li>Entwicklung nicht mehr erhältlicher Ersatzteile</li>
            <li>Änderung und Optimierung vorhandener CAD-Dateien</li>
          </ul>
        </article>
        <article class="cad-service-card">
          <span class="cad-service-number">02</span>
          <h3>Zeichnungen & Fertigung</h3>
          <ul>
            <li>Technische Zeichnungen und Fertigungszeichnungen</li>
            <li>Schweißzeichnungen und Schweißbaugruppen</li>
            <li>Blechabwicklungen für Laser- und Kantteile</li>
            <li>Baugruppen, Stücklisten und Montagezeichnungen</li>
            <li>Digitalisierung von Skizzen und alten Zeichnungen</li>
            <li>Vermessung und Nachkonstruktion vorhandener Bauteile</li>
          </ul>
        </article>
        <article class="cad-service-card">
          <span class="cad-service-number">03</span>
          <h3>Dateien & 3D-Druck</h3>
          <ul>
            <li>STEP / STP</li>
            <li>STL und 3MF</li>
            <li>DXF für Laser- und Kantteile</li>
            <li>Weitere Formate nach Absprache</li>
            <li>3D-Druck von Prototypen und Ersatzteilen</li>
            <li>Kleinserien nach Projektabsprache</li>
          </ul>
        </article>
      </div>
    </section>

    <section class="cad-experience">
      <div class="cad-experience-inner">
        <div>
          <p class="eyebrow">PRAXISNAHES ENGINEERING</p>
          <h2>Technik verstehen.<br /><span>Lösungen gestalten.</span></h2>
        </div>
        <div class="cad-experience-copy">
          <p>Erfahrung aus Maschinenbau, Sonderfahrzeugbau, Stahlbau und Landtechnik fließt in jedes Projekt ein – für Lösungen, die nicht nur auf dem Bildschirm funktionieren.</p>
          <div class="cad-tags"><span>Maschinenbau</span><span>Sonderfahrzeugbau</span><span>Stahlbau</span><span>Landtechnik</span></div>
        </div>
      </div>
    </section>

    <section id="cad-ablauf" class="how section-wrap cad-how">
      <div class="section-heading">
        <div><p class="eyebrow">EINFACH & TRANSPARENT</p><h2>Dein Projekt.<br />Drei klare <span>Schritte.</span></h2></div>
      </div>
      <div class="steps">
        <article class="step"><span class="step-number">01</span><h3>Idee teilen</h3><p>Melde dich mit deiner Idee, Skizze, Zeichnung oder vorhandenen Datei – auch ein erstes Gespräch ist unverbindlich.</p></article>
        <article class="step"><span class="step-number">02</span><h3>Lösung abstimmen</h3><p>Wir besprechen Anforderungen, gewünschte Ergebnisse und den passenden Leistungsumfang. Du erhältst einen fairen Festpreis vorab.</p></article>
        <article class="step"><span class="step-number">03</span><h3>Ergebnis erhalten</h3><p>Die Zusammenarbeit läuft deutschlandweit digital. Aufmaße vor Ort oder die Zusendung von Bauteilen sind nach Absprache möglich.</p></article>
      </div>
    </section>

    <section class="contact cad-contact">
      <div class="contact-copy">
        <p class="eyebrow">DEINE IDEE IST DER ANFANG</p>
        <h2>Was möchtest<br />du <span>konstruieren?</span></h2>
        <p>Schick mir deine Skizze, Zeichnung oder vorhandene Datei. Gemeinsam finden wir die passende Lösung.</p>
        <a class="button button-dark" :href="cadContactUrl" target="_blank" rel="noreferrer">CAD-Projekt anfragen <span aria-hidden="true">↗</span></a>
      </div>
      <div class="contact-aside cad-contact-aside">
        <span class="contact-star" aria-hidden="true">⌘</span>
        <p>KD-SERVICE<br /><strong>KONSTRUKTION & 3D-DRUCK</strong></p>
        <span class="contact-pin">Deutschlandweit digital</span>
      </div>
    </section>
  </main>

  <footer class="site-footer">
    <span class="brand footer-brand"><span class="brand-mark">KD<span>.</span></span><span class="brand-name">KD-SERVICE<span>KONSTRUKTION · EVENTVERLEIH</span></span></span>
    <p v-if="activeService === 'event'">Eventverleih für unvergessliche Feiern.</p>
    <p v-else>Konstruktion, technische Zeichnungen & 3D-Druck.</p>
    <a href="#start">Zurück nach oben ↑</a>
    <span class="copyright">© {{ new Date().getFullYear() }} KD-Service</span>
  </footer>
  </div>
</template>
