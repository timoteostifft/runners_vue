<template>
  <div id="container">
    <div id="background">
      <div id="content">
        <div id="title">
          <h3>Endereço</h3>
        </div>
        <div id="info">
          <p>
            Av. Independência, 1299 -
            <br />
            sala 502 - Independência
          </p>
        </div>
      </div>
      <div id="content">
        <div id="title">
          <h3>Contato</h3>
        </div>
        <div id="info">
          <a href="tel:(51)3024-7129">(51) 3024-7129</a> <br />
          <a href="mailto:atendimento@deliverit.com.br"> atendimento@deliverit.com.br </a>
        </div>
      </div>
      <div id="content">
        <div id="title">
          <h3>Acompanhe</h3>
        </div>
        <div id="info">
          <a href="https://www.facebook.com/deliverit.brasil/">
            <img alt="Facebook logo" src="../../assets/facebookIcon.png" />
          </a>
          <a href="https://www.instagram.com/deliverit.brasil/">
            <img alt="Instagram logo" src="../../assets/instagramIcon.png" />
          </a>
          <a href="https://twitter.com/">
            <img alt="Instagram logoTwitter" src="../../assets/twitterIcon.png" />
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AppFooter',
};
</script>

<style scoped lang="scss">
#container {
  width: 100%;

  margin-top: 60px;
  background: #e7eaee;
  border-top: 3px solid #3a628d;
  box-shadow: rgba(0, 0, 0, 0.4) 0px -5px 20px 0px;

  #background {
    height: 100%;
    max-width: 1120px;

    padding: 2rem 2rem;
    margin: 0 auto;

    @media (min-width: 844px) {
      display: flex;
      flex-direction: row;
      justify-content: space-between;
    }

    @media (max-width: 843px) {
      br {
        display: none;
      }
    }

    #title {
      display: inline-block;
      border-bottom: 1.5px solid #3a628d;
      color: #3a628d;

      height: 18px;

      h3 {
        font-size: 16.5px;
        font-weight: 600;
        line-height: 10px;
      }
    }

    #info {
      margin-top: 12px;
      color: #3a628d;

      @media (max-width: 843px) {
        margin-bottom: 30px;
      }

      p {
        font-size: 16.5px;
        font-weight: 400;
      }

      a {
        font-size: 16.5px;
        text-decoration: none;
        color: #3a628d;

        img {
          height: 2rem;
          width: auto;
          margin-right: 10px;
        }
      }
    }
  }
}
</style>
