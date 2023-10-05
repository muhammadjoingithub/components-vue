<template>
<div class="flexable">
<ul class="dropdown-menu flex ">
    <li v-for="link in links" :key="link.id" @mouseover="toggleDropdown(link.id)" @mouseleave="toggleDropdown(null)" class="transition duration-700 ease-in-out">
      <a :href="link.url" @click="highlightLink(link.id)" :class="{ 'active': link.id === activeLink }">{{ link.name }}</a>
            <ul v-if="link.id === activeLink" class="dropdown-list">
              <li v-for="source in link.sources" :key="source">{{ source }}</li>
            </ul>
    </li>
</ul>
</div>
</template>

<script>
export default {
  data() {
    return {
      links: [
        {
          id: 1,
          name: 'News',
          url: 'https://example.com/link1',
          sources: ['source 1', 'source 2', 'source 3']
        },
        {
          id: 2,
          name: 'Blog',
          url: 'https://example.com/link2',
          sources: ['source 4', 'source 5']
        },
        {
          id: 3,
          name: 'About',
          url: 'https://example.com/link3',
          sources: ['source 6', 'source 7', 'source 8']
        }
      ],
      activeLink: null
    };
  },
  methods: {
    toggleDropdown(linkId) {
      this.activeLink = linkId === this.activeLink ? null : linkId;
    },
    highlightLink(linkId) {
      this.activeLink = linkId;
    }
  }
};
</script>

<style>
.flexable{
    display: flex;
    
}
.dropdown-menu {
  list-style-type: none;
  padding: 0;
  margin: 0;
}

.dropdown-menu li {
  position: relative;
  padding: 10px;
}

.dropdown-menu li a {
  color: #000;
  text-decoration: none;
  display: inline-block;
}

.dropdown-menu li .active {
  color: #f00; 
}

.dropdown-list {
  position: absolute;
  top: 20px;
  left: 0;
  padding: 10px;
  background-color: #f5f5f5; 
  display: none;
}

.dropdown-menu li:hover .dropdown-list {
  display: block;
}
</style>