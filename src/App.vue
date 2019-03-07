<template>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/4.0.0-beta/css/bootstrap.min.css">
<link rel="stylesheet" href="https://unpkg.com/leaflet@1.2.0/dist/leaflet.css">
<script src="https://cdnjs.cloudflare.com/ajax/libs/vue/2.3.4/vue.min.js"></script>
<script src="https://unpkg.com/leaflet@1.2.0/dist/leaflet.js"></script>
<div class="container mt-3 mt-sm-5" id="app">
  <div class="row">
    <div class="col-md-9">
      <div class="map" id="map"></div>
    </div>
    <div class="col-md-3">
      <div
        class="form-check"
        v-for="layer in layers"
        :key="layer.id"
      >
        <label class="form-check-label">
          <input
            class="form-check-input"
            type="checkbox"
            v-model="layer.active"
            @change="layerChanged(layer.id, layer.active)"
          />
          {{ layer.name }}
        </label>
      </div>
    </div>
  </div>
</div>
</template>
