<script setup>
import { ref } from 'vue'
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
import {
  faArrowRight, faBars, faXmark, faBolt, faDroplet, faBuilding,
  faStore, faBoxesStacked, faBed, faBath, faCouch, faDoorOpen,
  faShieldHalved, faElevator, faPaintRoller, faLocationDot,
  faCartShopping, faGraduationCap, faHospital, faMosque, faBus
} from '@fortawesome/free-solid-svg-icons'
import { faInstagram, faFacebookF, faLinkedinIn } from '@fortawesome/free-brands-svg-icons'

const menuOpen = ref(false)
const nav = ['Home', 'About', 'Apartments', 'Shops', 'Amenities', 'Location', 'Gallery', 'Contact']
const features = [
  [faBolt, 'Silent generator', 'Inside building'],
  [faDroplet, 'Borehole water', 'Prepaid meter'],
  [faBuilding, '13 floors', 'Residential'],
  [faStore, 'Ground floor', 'Shops'],
  [faBoxesStacked, 'Basement', 'Storage units']
]
const amenities = [
  [faBolt, 'Silent generator'], [faDroplet, 'Borehole water'], [faShieldHalved, '24/7 security'],
  [faElevator, 'High-speed lifts'], [faPaintRoller, 'Modern finishes'], [faStore, 'Near key amenities'], [faLocationDot, 'Prime location']
]
const apartmentSpecs = [[faBed, '2 Bedrooms'], [faBath, '2 Bathrooms'], [faCouch, 'Unfurnished'], [faDoorOpen, 'Balcony']]
const landmarks = [[faCartShopping, 'Shopping Centre', '3 mins'], [faGraduationCap, 'Eastleigh High School', '5 mins'], [faHospital, 'Aga Khan Hospital', '7 mins'], [faMosque, 'Jamia Mosque', '5 mins'], [faBus, 'Eastleigh Bus Station', '5 mins']]
</script>

<template>
  <main>
    <header class="nav-shell">
      <a class="brand" href="#home" aria-label="Eastleigh Heights home">
        <span class="mark"><i></i><i></i><i></i><i></i></span>
        <span><b>EASTLEIGH<br>HEIGHTS</b><small>— 3RD STREET —</small></span>
      </a>
      <button class="menu" @click="menuOpen = !menuOpen" aria-label="Toggle navigation"><FontAwesomeIcon :icon="menuOpen ? faXmark : faBars" /></button>
      <nav :class="{ open: menuOpen }">
        <a v-for="item in nav" :key="item" :href="`#${item.toLowerCase()}`" @click="menuOpen = false">{{ item }}</a>
      </nav>
      <a class="outline-btn nav-cta" href="#contact">Enquire now <FontAwesomeIcon :icon="faArrowRight" /></a>
    </header>

    <section id="home" class="hero">
      <div class="hero-copy">
        <p class="eyebrow">Live <i></i> Work <i></i> Belong</p>
        <h1>Eastleigh<br>Heights</h1>
        <div class="street"><span></span>3rd Street<span></span></div>
        <h2>Modern Living in the Heart of Eastleigh</h2>
        <p class="lead">A landmark 13-floor residential development with premium retail spaces, designed for modern urban living.</p>
        <div class="actions">
          <a class="gold-btn" href="#apartments">View apartments <FontAwesomeIcon :icon="faArrowRight" /></a>
          <a class="outline-btn" href="#contact">Get in touch</a>
        </div>
      </div>
      <p class="hero-note">Prime location<br>Modern living<br>Greater possibilities</p>
      <div class="feature-row">
        <div v-for="([icon, title, sub]) in features" :key="title" class="feature">
          <strong><FontAwesomeIcon :icon="icon" /></strong><b>{{ title }}</b><small>{{ sub }}</small>
        </div>
      </div>
    </section>

    <section id="apartments" class="property-grid section-light">
      <article class="info-card apartment-copy">
        <p class="kicker">Featured residences</p>
        <h2>2-Bedroom Apartments<br>for Rent</h2>
        <p class="price">KES. 75,000 <small>per month</small></p>
        <div class="specs"><span v-for="([icon, label]) in apartmentSpecs" :key="label"><FontAwesomeIcon :icon="icon" /><small>{{ label }}</small></span></div>
        <div class="terms"><b>Payment terms</b><br>Two months deposit<br>Ready for occupation soon.</div>
        <a class="dark-btn" href="#contact">View floor plan <FontAwesomeIcon :icon="faArrowRight" /></a>
      </article>
      <div class="photo living"><span>Spacious living area</span></div>
      <div class="photo kitchen"><span>Modern kitchen space</span></div>
    </section>

    <section id="shops" class="split-section section-light">
      <article class="info-card">
        <p class="kicker">Business opportunity</p><h2>Retail Spaces<br>on Ground Floor</h2>
        <p>High visibility shops, ideal for retail, services, restaurants and lifestyle businesses.</p>
        <a class="dark-btn" href="#contact">View shop spaces <FontAwesomeIcon :icon="faArrowRight" /></a>
      </article>
      <div class="photo retail"><span>Vibrant ground-floor shopping</span></div>
    </section>

    <section class="split-section storage-row section-light">
      <article class="info-card">
        <p class="kicker">Extra room, downstairs</p><h2>Basement<br>Storage Units</h2>
        <p>Dedicated, secure storage units in the basement, ideal for businesses and residents.</p>
        <a class="dark-btn" href="#contact">Enquire about storage <FontAwesomeIcon :icon="faArrowRight" /></a>
      </article>
      <div class="storage-visual"><div class="door one"></div><div class="aisle"><span>Secure. Accessible. Practical.</span></div><div class="door two"></div></div>
    </section>

    <section id="amenities" class="amenities">
      <p class="kicker gold">Premium amenities</p>
      <h2>Comfort. Convenience. Peace of Mind.</h2>
      <div class="amenity-list"><div v-for="([icon, label]) in amenities" :key="label"><strong><FontAwesomeIcon :icon="icon" /></strong><span>{{ label }}</span></div></div>
    </section>

    <section id="location" class="location section-light">
      <article>
        <p class="kicker">Strategic location</p><h2>Connected to Everything<br>That Matters</h2>
        <p>Located on 3rd Street, Eastleigh, minutes from shopping centres, schools, hospitals, public transport and only a short drive to Nairobi CBD.</p>
        <a class="dark-btn" href="https://maps.google.com/?q=Eastleigh+3rd+Street+Nairobi" target="_blank" rel="noopener">View on Google Maps <FontAwesomeIcon :icon="faArrowRight" /></a>
      </article>
      <div class="map-card"><iframe title="Eastleigh Heights location on Google Maps" src="https://www.google.com/maps?q=Eastleigh%203rd%20Street%2C%20Nairobi%2C%20Kenya&z=15&output=embed" loading="lazy" referrerpolicy="no-referrer-when-downgrade" allowfullscreen></iframe></div>
      <article class="landmarks"><p class="kicker">Nearby landmarks</p><ul><li v-for="([icon, name, time]) in landmarks" :key="name"><span><FontAwesomeIcon :icon="icon" />{{ name }}</span><b>{{ time }}</b></li></ul></article>
    </section>

    <footer id="contact">
      <a class="brand footer-brand" href="#home"><span class="mark"><i></i><i></i><i></i><i></i></span><span><b>EASTLEIGH<br>HEIGHTS</b><small>— 3RD STREET —</small></span></a>
      <div class="contact-copy"><p>Ready to find your place?</p><a href="mailto:hello@eastleighheights.co.ke">hello@eastleighheights.co.ke</a></div>
      <div class="socials"><a href="#" aria-label="Instagram"><FontAwesomeIcon :icon="faInstagram" /></a><a href="#" aria-label="Facebook"><FontAwesomeIcon :icon="faFacebookF" /></a><a href="#" aria-label="LinkedIn"><FontAwesomeIcon :icon="faLinkedinIn" /></a><span>More than a home.<br>A brighter tomorrow.</span></div>
    </footer>
  </main>
</template>
