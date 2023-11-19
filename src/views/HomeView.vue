<script setup>
import CarouselItemComponent from '@/components/CarouselItemComponent.vue';
import CarouselComponent from '@/components/CarouselComponent.vue';
</script>

<template>
  <main class="x-home-view">
    <section class="hero">
      <div class="greetings">
        <div>
          <strong>Welcome</strong>
          <span> to the </span>
          <strong>Marigold Hope Foundation</strong>
        </div>
      </div>

      <img
        class="cover"
        src="@/assets/images/home-view-hero-cover.jpg"
        alt="Hero Cover"
      >
      
      <img
        class="alt"
        src="@/assets/images/home-view-hero-alt.jpg"
        alt="Hero Alt"
      >

      <div class="remark">
        <div>The Marigold Hope Foundation, since its establishment, has undertaken series of programmes all in the bid to eradicating poverty and improving livelihoods of vulnerable groups especially women and girls.</div>
      </div>

      <div class="stats">
        <span class="number">677</span>
        <span>Women have provided free entrepreneurial skills training in bridal clutch, make-ups, hairdressing, interior decoration, graphic designing, bead making, soap making and detergents to less privileged women and girls within various communities.</span>
      </div>

      <div class="donate">
        <a
          class="link"
          href="javascript:void(0);"
        >
          <span class="text">Donate to our cause</span>
        </a>
      </div>

      <div class="encouragement">
        <div class="text">
          <span>You're all encouraged to be a part of the </span>
          <em class="company">“Marigold Hope Foundation”</em>
          <span>.&nbsp;</span>
        </div>
      </div>
    </section>

    <section class="detail-section about">
      <div class="label">About</div>

      
      <div class="content">
        <div class="divider"></div>

        <p>Established 2009, the mandate of MHF is focused on the United Nations' Sustainable Development Goals (SDG), 1, 2, 4, 5 and 8. Marigold Hope Foundation is a non-profit organization that works in deprived communities with a focus of creating decent and sustainable jobs to women and girls, and providing children with educational materials.</p>

        <p>MHF is comprised of five officials namely; the CEO, project coordinator, secretary, assistant secretary and a financial officer andin addition six volunteers. We have three laptops, two desktop computers, one printer, seven office chairs and desks for our operations.</p>

        <p>The organization since its establishment has undertaken series of programmes all in the bid to eradicating poverty and improving livelihoods of vulnerable groups especially women and girls.</p>

        <p>We have organized a free breast cancer screening and education and an annual street feeding for the less privileged in our societies. Last year, MHF organized a party for the Dzorwulu Special School in Accra.</p>

        <p>The organization depends on its staff but ultimately by the CEO, friends and relatives to run it programmes.</p>

        <p>This year MHF hopes to train 120 young youths with different skills including male dominated fields for girls to create about 5000 jobs.</p>
      </div>
    </section>

    <section class="detail-section mission">
      <div class="label">Mission</div>

      
      <div class="content">
        <div class="divider"></div>

        <p>Our mission is to improve the livelihoods of vulnerable groups especially women and girls in society through education,skills training and contribute to the eradication of violence against women and girls.</p>
      </div>
    </section>

    <section class="detail-section vision">
      <div class="label">Vision</div>

      
      <div class="content">
        <div class="divider"></div>

        <p>Our vision is to see where every woman's dream is achievable by providing requisite and employable skills to eradicate Gender Based Violence (GBV).</p>
      </div>
    </section>


    <section class="events">
      <carousel-component #item-1>
        <carousel-item-component>
          <template #image>
              <img
                src="@/assets/images/home-view-event-image-1.jpg"
                alt="Event Image"
              >
          </template>

          <div class="place-time">Bubiashie, 19 Nov 2023</div>

          <div class="title">Some Cool Event</div>

          <div class="description">Lorem ipsum dolor sit amet consectetur adipisicing elit. Temporibus ad labore necessitatibus animi quasi maxime! Similique obcaecati doloribus reprehenderit ex quos deleniti repellendus vel maxime.</div>
        </carousel-item-component>
      </carousel-component>
    </section>
  </main>
</template>

<style>
.x-home-view > .hero {
  display: grid;
  grid-template-columns: 1fr;
}

.x-home-view > .hero > .greetings {
  border-bottom: 1px solid var(--x-foreground-color);
  font-size: 3.25rem;
  padding: 2.5rem 1.5rem;
}

.x-home-view > .hero > .cover {
  aspect-ratio: 3 / 4;
  border-bottom: 1px solid var(--x-foreground-color);
  display: block;
  max-height: 27.5rem;
  object-fit: cover;
  object-position: right;
  width: 100%;
}

.x-home-view > .hero > .alt {
  aspect-ratio: 4 / 3;
  border-bottom: 1px solid var(--x-foreground-color);
  display: block;
  max-height: 24.5rem;
  object-fit: cover;
  object-position: right;
  width: 100%;
}

.x-home-view > .hero > .remark {
  border-bottom: 1px solid var(--x-foreground-color);
  padding: 1.5rem;
}

.x-home-view > .hero > .stats {
  align-items: center;
  border-bottom: 1px solid var(--x-foreground-color);
  display: flex;
  gap: 0.5rem;
  padding: 1.5rem;
}

.x-home-view > .hero > .stats > .number {
  font-size: 2.5rem;
  font-weight: 500;
  writing-mode: sideways-lr;
}

.x-home-view > .hero > .donate {
  align-items: center;
  border-bottom: 1px solid var(--x-foreground-color);
  display: flex;
  gap: 0.5rem;
  justify-content: center;
  padding: 1.5rem;
}

.x-home-view > .hero > .donate > .link {
  align-items: center;
  background-color: var(--x-foreground-color);
  border-radius: 100vmax;
  color: var(--x-background-color);
  display: flex;
  font-weight: 500;
  height: 12.5rem;
  justify-content: center;
  text-decoration: none;
  width: 12.5rem;
}

.x-home-view > .hero > .donate > .link > .text {
  rotate: z -25deg;
}

.x-home-view > .hero > .donate > .link:hover {
  background-color: var(--x-primary-color);
  color: var(--x-primary-complement-color);
}

.x-home-view > .hero > .encouragement {
  align-items: center;
  border-bottom: 1px solid var(--x-foreground-color);
  display: flex;
  gap: 0.75rem;
  justify-content: center;
  padding: 1.5rem;
  width: 100%;
}

.x-home-view > .hero > .encouragement > .text {
  text-align: center;
}

.x-home-view > .hero > .encouragement > .text > .company {
  font-weight: 500;
}

.x-home-view > .hero > .encouragement::before {
  content: '✦✦';
  font-size: 1.5rem;
}

.x-home-view > .hero > .encouragement::after {
  content: '✦✦';
  font-size: 1.5rem;
}

.x-home-view > .detail-section {
  display: grid;
  gap: 2.5rem;
  grid-template-columns: [ content-start label-start ] 1fr [ content-end label-end ];
  grid-template-rows: [ label-start ] auto [ label-end content-start ] auto [ content-end ];
  padding: 2.5rem 1.5rem;
}

.x-home-view > .detail-section > .label {
  font-weight: 500;
  grid-area: label
}

.x-home-view > .detail-section > .content {
  grid-area: content;
  margin: 0px auto;
  max-width: 640px;
}

.x-home-view > .detail-section > .content > .divider {
  border-bottom: 1px solid var(--x-foreground-color);
  margin-bottom: 2.5rem;
  width: 15rem;
}

.x-home-view > .events {
  padding: 2.5rem 1.5rem;
}

@media screen and (min-width: 768px) {
  .x-home-view > .hero {
    grid-template-columns: repeat(2, 1fr);
  }

  .x-home-view > .hero > .greetings {
    align-items: center;
    border-right: 1px solid var(--x-foreground-color);
    display: flex;
  }

  .x-home-view > .hero > .cover {
    aspect-ratio: initial;
    height: 100%;
  }

  .x-home-view > .hero > .alt {
    aspect-ratio: initial;
    border-right: 1px solid var(--x-foreground-color);
    height: 100%;
  }

  .x-home-view > .hero > .remark {
    align-items: center;
    display: flex;
  }

  .x-home-view > .hero > .stats {
    border-right: 1px solid var(--x-foreground-color);
  }

  .x-home-view > .hero > .encouragement {
    grid-column: span 2;
    justify-self: center;
  }

  .x-home-view > .detail-section {
    grid-template-columns: [ label-start ] auto [ label-end content-start ] 1fr [ content-end ];
    grid-template-rows: [ content-start label-start ] auto [ content-end label-end ];
  }

  .x-home-view > .detail-section > .label {
    margin-top: 2.5rem;
  }
}

@media screen and (min-width: 992px) {
  .x-home-view > .hero {
    grid-template-columns: 4fr 5fr 5fr 4fr;
  }

  .x-home-view > .hero > .greetings {
    font-size: 3.5rem;
    grid-column: span 2;
  }

  .x-home-view > .hero > .cover {
    grid-column: span 2;
  }

  .x-home-view > .hero > .remark {
    border-right: 1px solid var(--x-foreground-color);
  }

  .x-home-view > .hero > .encouragement {
    grid-column: span 4;
  }

  .x-home-view > .events {
    padding: 2.5rem;
  }
}

@media screen and (min-width: 1200px) {
  .x-home-view > .hero > .greetings {
    font-size: 4.25rem;
    padding: 2.5rem;
  }

  .x-home-view > .hero > .cover {
    max-height: 32.5rem;
  }

  .x-home-view > .hero > .encouragement {
    padding: 1.5rem 2.5rem;
  }

  .x-home-view > .detail-section > .content {
    max-width: 768px;
  }
}

@media screen and (min-width: 1600px) {
  .x-home-view > .hero > .greetings {
    font-size: 5rem;
  }

  .x-home-view > .detail-section > .content {
    max-width: 992px;
  }
}
</style>
