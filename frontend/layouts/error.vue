<template>
  <div>
    <h1
      class="text-4xl font-bold my-5"
      data-aos="fade-right"
      data-aos-duration="500"
    >
      Tentang
    </h1>
    <h3
      class="text-xl font-medium"
      data-aos="fade-right"
      data-aos-duration="1000"
    >
        <p>
      TanGeo adalah aplikasi peta online gratis yang diciptakan oleh Mahasiswa Gunadarma Karawaci. TanGeo dapat diakses melalui browser web untuk perangkat desktop dan perangkat mobile . Anda dapat menggunakan TanGeo untuk mendapatkan informasi tentang wisata untuk daerah khusus Tangerang.
          </p>
    </h3>

    <section class="pt-20 pb-20">
      <div
        class="flex flex-wrap"
        data-aos="zoom-in-up"
        data-aos-duration="1000"
      >
        <div
          class="w-full md:w-2/12 lg:w-2/12 lg:mb-0 mb-12 px-4"
          v-for="(berug, index) in tim"
          :key="index"
          @click="eksekusi(berug, index)"
        >
          <div
            class="px-6 cursor-pointer transform hover:scale-105 duration-500"
          >
            <img
              :src="berug.foto"
              class="shadow-lg rounded-full mx-auto w-32 h-32"
            />
            <div class="pt-6 text-center">
              <h5 class="text-md font-bold text-gray-700">
                {{ berug.nama }}
              </h5>
              <p class="mt-1 text-sm text-gray-400 uppercase font-semibold">
                {{ berug.posisi }}
              </p>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import udin from "@/assets/img/tim/Udin.png";
import arkan from "@/assets/img/tim/Arkan.png";
import jack from "@/assets/img/tim/Jacobus.png";
import agil from "@/assets/img/tim/Agil.png";
import hugo from "@/assets/img/tim/Hugo.png";
import rafi from "@/assets/img/tim/Rafi.jpg";

export default {
  head: {
    title: "Tentang",
  },
  layout: "visitor",
  data() {
    return {
      tim: [
        {
          nama: "Alifahdun Hamzah",
          posisi: "System Analyst",
          foto: rafi,
        },
        {
          nama: "Arkan Amir",
          posisi: "Requirement Gathering",
          foto: rafi,
        },
        {
          nama: "Hugo Agung Hokiarto",
          posisi: "Software Design",
          foto: rafi,
        },
        {
          nama: "Fikri Wanagiel",
          posisi: "Module Design, Ketua",
          foto: rafi,
        },
        {
          nama: "Jacobus Hans Gradianto",
          posisi: "Backend Dev",
          foto: rafi,
        },
        {
          nama: "Rafi Priatna Kasbiantoro",
          posisi: "Frontend Dev, UAT",
          foto: rafi,
        },
      ],
    };
  },
  methods: {
    eksekusi(data, index) {
      this.$swal({
        icon: "success",
        title: "Terpilih",
        text: `Kamu sudah memilih ${data.nama} untuk dieksekusi.`,
        confirmButtonText: "Kembali ke beranda.",
      }).then(() => {
        this.$router.push("/");
      });
    },
  },
};
</script>