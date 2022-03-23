<template>
  <div id="container">
    <div id="background">
      <div id="content">
        <div id="title">
          <h3>Endereço</h3>
        </div>
        <div id="info">
          <p>
            Av. Independência, 1299 - sala 502 - Independência
          </p>
        </div>
      </div>
      <div id="content">
        <div id="title">
          <h3>Contato</h3>
        </div>
        <div id="info">
          <a href="tel:(51)3024-7129">(51) 3024-7129</a> <br />
            <a href="mailto:atendimento@deliverit.com.br">
              atendimento@deliverit.com.br
            </a>
        </div>
      </div>
      <div id="content">
        <div id="title">
          <h3>Acompanhe</h3>
        </div>
        <div id="info">
          <a href="https://twitter.com/camaqua_prefa">
            <img alt="Facebook logo" src="../assets/facebookIcon.png">
          </a>
          <a href="https://www.facebook.com/prefeituradecamaqua">
            <img alt="Instagram logo" src="../assets/instagramIcon.png">
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
#container{
  width: 100%;

  height: 100%;
  background: #e7eaee;
  border-top: 3px solid #3a628d;
  box-shadow: rgba(0, 0, 0, 0.4) 0px -5px 20px 0px;

  #background{
    height: 100%;
    max-width: 1120px;

    margin: 0 auto;
    padding: 1rem;

    #content{

      & + #content{

        margin-top: 5px;
    }

    #title{
      display: inline-block;
      border-bottom: 1.5px solid #3a628d;
      color: #3a628d;

      h3{
        font-size: 16.5px;
        font-weight: 600;
        line-height: 10px;
      }
    }

    #info{
      margin-top: 12px;
      color: #3a628d;

      p{
        font-size: 16.5px;
        font-weight: 400;
      }

      a{
        font-size: 16.5px;
        text-decoration: none;
        color: #3a628d;

        img{
          height: 2rem;
          width: auto;
          margin-right: 10px;
        }
      }
    }
  }
  }
}
</style>
