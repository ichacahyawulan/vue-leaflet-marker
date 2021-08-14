<template>
    <div class="map">
        <h2>Map using leaflet and vue</h2>
        <div style="height: 500px; width: 100%">
            <l-map :zoom="zoom" :center="center">
            <l-marker v-for="latlong in kecamatan" :key="latlong.koordinat" :lat-lng="latlong.koordinat">
                <l-popup>
                    <div @click="innerClick">
                        {{ latlong.nama }}
                        <!-- <p v-show="showParagraph">
                        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque
                        sed pretium nisl, ut sagittis sapien. Sed vel sollicitudin nisi.
                        Donec finibus semper metus id malesuada.
                        </p> -->
                    </div>
                </l-popup>
            </l-marker>
            <l-tile-layer :url="url" :attribution="attribution"></l-tile-layer>
            </l-map>
        </div>
    </div>
</template>

<script>
export default {
    data () {
        return {
        url:'http://{s}.tile.osm.org/{z}/{x}/{y}.png',
        attribution:'© <a href="http://osm.org/copyright">OpenStreetMap</a> contributors',
        zoom: 12,
        center: [-6.93,107.60],
        kecamatan: [
            {
                koordinat: [-6.93,107.57],
                nama: "Bandung Kulon"
            },
            {
                koordinat: [-6.94,107.58],
                nama: "Babakan Ciparay"
            },
            {
                koordinat: [-6.94,107.59],
                nama: "Bojongloa Kaler"
            },
            {
                koordinat: [-6.94,107.60],
                nama: "Bojongloa Kidul"
            },
            {
                koordinat: [-6.93,107.60],
                nama: "Astana Anyar"
            },
            {
                koordinat: [-6.95,107.61],
                nama: "Regol"
            },
            {
                koordinat: [-6.93,107.62],
                nama: "Lengkong"
            },
            {
                koordinat: [-6.96,107.64],
                nama: "Bandung Kidul"
            },
            {
                koordinat: [-6.96,107.67],
                nama: "Buah Batu"
            },
            {
                koordinat: [-6.95,107.68],
                nama: "Rancasari"
            },
            {
                koordinat: [-6.96,107.69],
                nama: "Gedebage"
            },
            {
                koordinat: [-6.93,107.72],
                nama: "Cibiru"
            },
            {
                koordinat: [-6.94,107.70],
                nama: "Panyileukan"
            },
            {
                koordinat: [-6.91,107.70],
                nama: "Ujung Berung"
            },
            {
                koordinat: [-6.92,107.70],
                nama: "Cinambo"
            },
            {
                koordinat: [-6.92,107.69],
                nama: "Arcamanik"
            },
            {
                koordinat: [-6.90,107.67],
                nama: "Antapani"
            },
            {
                koordinat: [-6.90,107.68],
                nama: "Mandalajati"
            },
            {
                koordinat: [-6.90,107.68],
                nama: "Kiaracondong"
            },
            {
                koordinat: [-6.94,107.64],
                nama: "Batununggal"
            },
            {
                koordinat: [-6.91,107.62],
                nama: "Sumur Bandung"
            },
            {
                koordinat: [-6.91,107.57],
                nama: "Andir"
            },
            {
                koordinat: [-6.91,107.60],
                nama: "Cicendo"
            },
            {
                koordinat: [-6.90,107.61],
                nama: "Bandung Wetan"
            },
            {
                koordinat: [-6.90,107.64],
                nama: "Cibeunying Kidul"
            },
            {
                koordinat: [-6.89,107.63],
                nama: "Cibeunying Kaler"
            },
            {
                koordinat: [-6.88,107.61],
                nama: "Coblong"
            },
            {
                koordinat: [-6.89,107.59],
                nama: "Sukajadi"
            },
            {
                koordinat: [-6.87,107.58],
                nama: "Sukasari"
            },
            {
                koordinat: [-6.87,107.60],
                nama: "Cidadap"
            }
        ],
        bounds: null
        };
    }
}
</script>