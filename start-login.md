<html>
<head>
    <title>UX Test</title>
        <meta charset="utf8">
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <link href="https://cdn.jsdelivr.net/webjars/org.webjars.npm/roboto-fontface/0.10.0/css/roboto/roboto-fontface.css" rel="stylesheet">
        <link href="https://cdn.jsdelivr.net/webjars/org.webjars.npm/mdi__font/5.0.45/css/materialdesignicons.css" rel="stylesheet">
        <link href="https://cdn.jsdelivr.net/webjars/org.webjars.npm/vuetify/2.3.19/dist/vuetify.css" rel="stylesheet">
        <link href="/img/favicon.png" rel="icon">
        <script src="https://cdn.jsdelivr.net/webjars/org.webjars.npm/vue/2.6.10/dist/vue.js"></script>
        <script src="https://cdn.jsdelivr.net/webjars/org.webjars.npm/axios/0.19.0/dist/axios.min.js"></script>
        <script src="https://cdn.jsdelivr.net/webjars/org.webjars.npm/vuetify/2.3.19/dist/vuetify.js"></script>
        <script src="https://cdn.jsdelivr.net/webjars/org.webjars.npm/chart.js/2.9.4/dist/Chart.min.js"></script>
        <script src="https://cdn.jsdelivr.net/webjars/org.webjars.npm/vue-chartjs/3.5.0/dist/vue-chartjs.min.js"></script>
        <script src="https://cdn.jsdelivr.net/webjars/org.webjars.npm/moment/2.24.0/min/moment.min.js"></script>
</head>
<body>
    <div id="vue">
        <header>
            This is a demo product
        </header>
        <div class="separator"></div>
        <main>
            <p>Since this is just a demo product, it's not possible to add it or open it.</p>
        </main>
    </div>
    <script>
        const urlParams = new URLSearchParams(window.location.search);
        const orgAndProduct = urlParams.get("id");
        const organization = orgAndProduct.split("-")[0];
        const product = orgAndProduct.replace(organization + "-", "");
        const orgs = {
            "aamii": {
                name: "AAmii",
                color: "#1b961b",
                products: [
                    {id: "child-tracker"},
                    {id: "travel-tracker"},
                ]
            },
            "foner": {
                name: "Foner",
                color: "#d870a0",
                products: [
                    {id: "call-logs"},
                    {id: "google-calendar"},
                ]
            },
            "spamblam": {
                name: "SpamBlam",
                color: "#2a2ae0",
                products: [
                    {id: "sms"},
                    {id: "voice"},
                ]
            },
            "teletech": {
                name: "TeleTech",
                color: "#4b5ce2",
                products: [
                    {id: "smart-home"},
                    {id: "stroke-detect"},
                ]
            },
            "voxcom": {
                name: "Voxcom",
                color: "#d0841d",
                products: [
                    {id: "clean-audio"},
                    {id: "slack-phone"},
                ]
            },
        }
        
        const vue = new Vue({
            el: "#vue",
            data: {},
            created() {
                this.org = organization;
                this.name = orgs[organization].name;
                this.products = orgs[organization].products;
                document.documentElement.style.setProperty("--color-brand", orgs[organization].color);
            }
        });
    </script>
        <style>
            * {
                box-sizing: border-box;
            }
            :root {
              --color-brand: black;
            }
            html {
                background: var(--color-brand);
                font-family: "Roboto", sans-serif;
                font-size: 16px;
                line-height: 1.5;
                color: rgba(0,0,0,0.8);
                padding: 20px;
            }
            body {
                padding: 32px;
                max-width: 1024px;
                margin: 20px auto;
                background: #fff;
                border-radius: 10px;
                box-shadow: 0 2px 20px rgba(0, 0, 0, 0.3);
            }
            header {
                font-size: 20px;
                display: flex;
                justify-content: space-around;
                align-items: center;
            }
            header img {
                display: block;
                height: 60px;
            }
            header a {
                display: inline-block;
                padding: 16px;
                text-decoration: none;
                color: var(--color-brand);
            }
            .separator {
                margin: 20px 0;
                height: 2px;
                background: var(--color-brand);
                border-radius: 4px;
            }
            h1 {
                margin-top: 42px;
                font-weight: 400;
                font-size: 42px;
            }
            h2, h3 {
                margin-top: 32px;        
            }
            .product-card {
                padding: 20px;
                margin: 20px 0;
                background: #fff;
                border-radius: 4px;
                box-shadow: 0 1px 5px rgba(0,0,0,0.2);
                text-transform: capitalize;
                display: flex;
                align-items: center;
            }
            .product-card img {
                height: 100px;
                margin-right: 20px;
            }
            .product-card strong {
                font-size: 24px;
            }
            ul {
                margin-left: 40px;
            }
    </style>
</body>
</html>
