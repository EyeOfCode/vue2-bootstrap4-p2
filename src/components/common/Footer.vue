<template>
  <footer class="footer pt-5">
    <div class="container">
      <div class="row">
        <div class="col-12 col-sm-4 col-md-3 col-lg-2">
          <img
            style="max-width: 139px; position: relative; bottom: 27px"
            src="@/assets/images/Kisankonnect_logo_footer.png"
            alt="kisankonnect-logo"
          />
        </div>
        <div class="col-lg-2 col-sm-4 footer_menu_div">
          <h5>Menu</h5>
          <ul class="footer_menu">
            <li>Home</li>
            <li>About Us</li>
            <li>Contact Us</li>
            <li>FAQs</li>
            <li>Why</li>
            <li>KisanKonnect?</li>
          </ul>
        </div>
        <div class="col-lg-5 col-sm-4 footer_menu_div">
          <h5>Contacts</h5>
          <p>
            <strong>KisanKonnect Corporate Office</strong><br />
            Plot no. C-10, TTC Industrial Estate,<br />
            MIDC, Pawne, Koperkhairne, Navi Mumbai,<br />
            Maharashtra - 400705<br />
          </p>
          <p>
            <a href="tel:+9118002670997" title="customer care number"
              >1800 267 0997</a
            ><br />
            <a
              href="mailto:customercare@kisankonnect.in"
              title="customer care email"
              >customercare@kisankonnect.in</a
            >
          </p>
        </div>
      </div>
      <div class="row">
        <div class="col-12 col-lg-2"></div>
        <div class="col-6 col-lg-6">
          <div class="footer_item">
            <div class="get_the_app text-center">
              <h3>DOWNLOAD THE APP</h3>
              <div class="content">
                <ul class="social-icons">
                  <li class="social-btn">
                    <img src="@/assets/images/App-store.png" alt="App-store" />
                  </li>
                  <li class="social-btn">
                    <img
                      src="@/assets/images/Google-play.png"
                      alt="Google-play"
                    />
                  </li>
                  <li class="social-btn socialbtn_btn">
                    <img
                      src="@/assets/icons/facebook-ic.svg"
                      alt="facebook-ic"
                    />
                  </li>
                  <li class="social-btn socialbtn_btn">
                    <img src="@/assets/icons/insta.png" alt="insta" />
                  </li>
                  <li class="social-btn socialbtn_btn">
                    <img src="@/assets/icons/linkedin.png" alt="linkedin" />
                  </li>
                  <li class="social-btn socialbtn_btn">
                    <img src="@/assets/icons/twitter-ic.svg" alt="twitter-ic" />
                  </li>
                </ul>
                <p>
                  © 2023, KisanKonnect |
                  <a href="#" class="cursor-pointer text-decoration-none"
                    >Privacy Policy</a
                  >
                  | Sitemap |
                  <a href="#" class="cursor-pointer text-decoration-none"
                    >Terms & Conditions</a
                  >
                </p>
              </div>
            </div>
          </div>
        </div>
        <div class="col-6 col-lg-4">
          <div class="footer_item footer_menu">
            <div class="footer-img">
              <img
                src="@/assets/images/footer-img-second.png"
                alt="footer-img-second"
              />
            </div>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'Footer',
};
</script>

<style scoped>
.footer-img {
  position: relative;

  img {
    width: 432px;
    position: absolute;
    bottom: -193px;
    left: 0;
  }
}
.socialbtn_btn {
  padding-left: 15px;
  vertical-align: unset;
  position: relative;
}
.social-icons {
  display: flex;
  align-items: center;
  list-style-type: none;
  padding-left: 0;
}
.social-btn {
  margin-right: 10px;

  img {
    width: 100%;
    padding-right: 0;
  }
}
.footer {
  color: #fff;
  padding: 50px 0 22px;
  position: relative;
  width: 100%;
  display: flex;
  overflow: hidden;
  margin-top: 90px;
}
.get_the_app {
  position: relative;
  color: #fff;

  h3 {
    text-align: left;
    font-size: 21px;
    margin: 3px 0 25px;
  }

  p {
    text-align: left;
    padding: 10px 0 0;
    font-size: 14px;
  }

  a {
    color: #fff;
  }

  a:hover {
    text-decoration: none;
  }
}
.footer_menu {
  list-style: none;
  position: relative;
  border: 0 none;
  margin: 0;
  padding: 0;
}
.footer_item p {
  font-weight: 400;
  margin-bottom: 10px;
  color: #fff;
}
.footer_menu li {
  padding: 3px 0;
}
.footer_menu_div {
  position: relative;

  a {
    color: #fff;
  }
  a:hover {
    text-decoration: none;
  }
}
.footer_menu_div:before {
  content: '';
  min-height: 90%;
  position: absolute;
  left: -10px;
  top: 33px;
  display: block;
}
.footer:before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: #26a649;
  background-image: linear-gradient(327deg, #1e8c42 0%, #0b7c3c 74%);
  border-radius: 50% 50% 0 0 / 100% 100% 0 0;
  transform: scaleX(1.5);
}
</style>
