<template>
  <footer>
    <div class="container container--footer">
        <div class="d-flex flex-column flex-lg-row justify-content-between align-items-center">
            <div class="py-3">
                <img src="../assets/images/Logo.svg" alt="Brilo" width="208" height="65">
            </div>
            <ul v-if="footerLinks" class="Footer-navigation py-3">
                <li v-for="footerLink in footerLinks" :key="footerLink">
                    <a :href=footerLink.curl class="Link">{{ footerLink.text }}</a>
                </li>
            </ul>
                <p class="Footer-copyright py-3">&copy; 2024 Thalion All rights reserved.</p>
        </div>

    </div>
  </footer>
</template>

<script>
export default {
    data() {
        return {
            footerLinks: [
                {
                    text: "První proklik",
                    curl: "#"
                },
                {
                    text: "Druhý proklik",
                    curl: "#"
                },
                {
                    text: "Třetí proklik",
                    curl: "#"
                }
            ]
        }
    }
}
</script>

<style scoped lang="less">
    .Footer-navigation {
        display: flex;
        flex-direction: row;
        justify-content: center;
        gap: 40px;
        flex-wrap: wrap;
        padding-left: 0;
        margin-bottom: 0;

        li {
            display: flex;
            align-items: center;
        }
    }

    .Footer-copyright {
        margin-bottom: 0;
    }

</style>