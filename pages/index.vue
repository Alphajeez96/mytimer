<template>
  <div class="container">
    <el-card class="box-card">
      <div class="time-holder">
        <div>
          <h2>Pacific</h2>

          <div class="headers">
            <p>{{ pt }}</p>
          </div>
        </div>

        <div class="ml-auto">
          <h2>Naija</h2>

          <div class="headers">
            <p>{{ nt }}</p>
          </div>
        </div>
      </div>
    </el-card>
  </div>
</template>

<script>
import moment from "moment-timezone";
export default {
  data: () => ({
    nt: "",
    pt: ""
  }),

  mounted: function() {
    window.setInterval(() => {
      this.getTime();
    }, 1000);
  },

  methods: {
    getTime() {
      this.nt = moment().format("hh:mm:ss A");
      this.pt = moment()
        .tz("America/Phoenix")
        .format("hh:mm:ss A");
    }
  }
};
</script>

<style>
.container {
  display: flex;
  justify-content: center;
  margin: 100px;
}

.time-holder {
  display: flex;
  flex-wrap: wrap;
}
.headers {
  margin-top: 20px;
}
.headers p {
  font-size: 1.2rem;
}

.text {
  font-size: 14px;
}

.item {
  padding: 18px 0;
}

.box-card {
  width: 480px;
}
.ml-auto {
  margin-left: auto;
}

@media (max-width: 575.98px) {
  h2 {
    margin-top: 10px;
  }
  p {
    font-size: 1rem;
  }
}

@media (min-width: 576px) and (max-width: 767.98px) {
}
</style>
