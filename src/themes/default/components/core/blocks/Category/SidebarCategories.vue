<template>
  <div>
    <div class="h5">Categories</div>
    <router-link
      class="block no-underline category-link"
      :to="localizedRoute({
        name: 'category',
        params: {
          slug: parentCategory.slug,
        }
      })"
      data-testid="productLink"
    >
      <span>{{ parentCategory.name }}</span>
    </router-link>
    <ul id="sidebar-categories">
      <li v-for="category in categories" :key="category.id">
        <router-link
          class="block no-underline category-link"
          :to="localizedRoute({
            name: 'category',
            params: {
              slug: category.slug,
            }
          })"
          data-testid="productLink"
        >
          <span>{{ category.name }}</span>
        </router-link>
      </li>
    </ul>
  </div>
</template>

<script>
import Category from '@vue-storefront/core/pages/Category'

export default {
  mixins: [Category]
}
</script>
