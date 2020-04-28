<template>
  <div class="packages">
    <div class="packages-title">
      <h1 class="packages-title-text">
        Shop Our Packages
      </h1>
    </div>
    <div class="packages-container">
      <PackageBlock
        v-for="pkg in packages"
        v-bind:pkg="pkg"
        v-bind:key="pkg.id"
        class="packages-block">
      </PackageBlock>
    </div>
  </div>
</template>

<script>
  import PackageBlock from '@/components/PackageBlock.vue';

  export default {
    name: 'Packages',
    data() {
      return {
        fightCampPersonal: {
          title: 'FightCamp You',
          id: 'fightcampYou',
          text: 'Everything You Need to Hit Your Goals',
          product: {
            price: 222200,
            monthly: 9000,
            months: 24,
          },
          thumbnails: [
            {
              name: 'Full Package',
              img_url: 'https://cdn3.joinfightcamp.com/1200x0/v4/fc-products-gym-setup-001.jpg',
            },
            {
              name: 'Punch Trackers',
              img_url: 'https://cdn3.joinfightcamp.com/1578x0/v4/fc-products-trackers-004.jpg',
            },
            {
              name: 'Free-Standing Bag',
              img_url: 'https://cdn3.joinfightcamp.com/1578x0/v4/fc-products-bag-004.jpg',
            },
            {
              name: 'Premium Boxing Gloves',
              img_url: 'https://cdn3.joinfightcamp.com/1578x0/v4/fc-products-gloves-001.jpg',
            },
          ],
          included: [
            {
              name: 'Punch Trackers',
              included: true,
            },
            {
              name: 'Quick Wraps',
              included: true,
            },
            {
              name: 'Free-Standing Bag',
              included: true,
            },
            {
              name: 'Heavy Workout Mat',
              included: true,
            },
            {
              name: 'Premium Boxing Gloves',
              included: true,
            },
            {
              name: 'Additional Premium Boxing Gloves',
              included: false,
            },
            {
              name: 'Additional Quick Wraps',
              included: false,
            },
            {
              name: 'Kids Boxing Gloves',
              included: false,
            },
          ],
        },
        fightCampConnect: {
          title: 'FightCamp Lite',
          id: 'fightcampLite',
          product: {
            price: 60900,
            monthly: 7658,
            months: 12,
          },
          text: 'Perfect for Boxers Who Crave Next-Level Training',
          thumbnails: [
            {
              name: 'Full Package',
              img_url: 'https://cdn3.joinfightcamp.com/1000x0/v4/fc-products-connect-setup-001.jpg',
            },
            {
              name: 'Punch Trackers',
              img_url: 'https://cdn3.joinfightcamp.com/1578x0/v4/fc-products-trackers-004.jpg',
            },
            {
              name: 'Quick Wraps',
              img_url: 'https://cdn3.joinfightcamp.com/1578x0/v4/fc-products-wraps-001.jpg',
            },
            {
              name: 'Quick Wraps',
              img_url: 'https://cdn3.joinfightcamp.com/1578x0/v4/fc-products-wraps-003.jpg',
            },
          ],
          included: [
            {
              name: 'Punch Trackers',
              included: true,
            },
            {
              name: 'Quick Wraps',
              included: true,
            },
            {
              name: 'Free-Standing Bag',
              included: false,
            },
            {
              name: 'Heavy Workout Mat',
              included: false,
            },
            {
              name: 'Premium Boxing Gloves',
              included: false,
            },
            {
              name: 'Additional Premium Boxing Gloves',
              included: false,
            },
            {
              name: 'Additional Quick Wraps',
              included: false,
            },
            {
              name: 'Kids Boxing Gloves',
              included: false,
            },
          ],
        },
        fightCampTribe: {
          title: 'FightCamp Them',
          headline: 'Popular',
          product: {
            price: 534900,
            monthly: 10621,
            months: 24
          },
          id: 'fightcamp_tribe',
          text: 'Perfect for Households Who Are Stronger Together',
          thumbnails: [
            {
              name: 'Full Package',
              img_url: 'https://cdn3.joinfightcamp.com/1000x0/v4/fc-products-family-setup-001.jpg'
            },
            {
              name: 'Punch Trackers',
              img_url: 'https://cdn3.joinfightcamp.com/1578x0/v4/fc-products-trackers-004.jpg'
            },
            {
              name: 'Free-Standing Bag',
              img_url: 'https://cdn3.joinfightcamp.com/1578x0/v4/fc-products-bag-004.jpg'
            },
            {
              name: 'Quick Wraps',
              img_url: 'https://cdn3.joinfightcamp.com/1578x0/v4/fc-products-wraps-003.jpg'
            },
          ],
          included: [
            {
              name: 'Punch Trackers',
              included: true,
            },
            {
              name: 'Quick Wraps',
              included: true,
            },
            {
              name: 'Free-Standing Bag',
              included: true,
            },
            {
              name: 'Heavy Workout Mat',
              included: true,
            },
            {
              name: 'Premium Boxing Gloves',
              included: true,
            },
            {
              name: 'Additional Premium Boxing Gloves',
              included: true,
            },
            {
              name: 'Additional Quick Wraps',
              included: true,
            },
            {
              name: 'Kids Boxing Gloves',
              included: true,
            },
          ],
        },
      }
    },
    computed: {
        packages() { return [this.fightCampPersonal, this.fightCampConnect, this.fightCampTribe] },
    },
    components: {
      PackageBlock
    },
  };
</script>

<style scoped lang="scss">
  .packages {
    background-color: #dddfe1;
    justify-content: center;
    padding: 1.5rem 0 5rem 0;

    &-title {
      align-items: center;
      color: #0f1e3c;
      flex-direction: column;
      display: flex;
    }

    &-title-text {
      font-size: 40px;
      margin: 1rem 0;

      @media (min-width: 768px) and (max-width: 1200px) {
        font-size: 60px;
      }

      @media (min-width: 1200px) {
        font-size: 60px;
      }
    }

    &-container {
      display: flex;
      flex-direction: column-reverse;
      align-items: center;

      @media  (min-width: 768px) and (max-width: 1200px) {
        flex-direction: row;
        padding: 1rem 0;
        justify-content: center;
      }

      @media  (min-width: 1200px) {
        flex-direction: row;
        padding: 1% 3%;
        justify-content: center;
      }
    }
  }
</style>
