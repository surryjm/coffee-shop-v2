<!-- INSTAGRAM COMPONENT -->
<template>

  <!-- Note title is not returned from the API, so I used the photo URL instead -->
  <!-- Custom attributes for photographer, photographer URL and photographer ID -->
    <img 
      :src="photo.src.medium"
      :alt="photo.url"
      :data-photographer="photo.photographer"
      :data-photographer-url="photo.photographer_url"
      :data-photographer-id="photo.photographer_id"
      />
      
</template>

<script>

export default {
  name: 'InstagramFeed',
  props: {
    photo: Object
  }
}
</script>

