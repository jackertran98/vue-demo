<template>
  <div class="hello">
    <div className="container home-container">
      <div className="wso2-logo-block">
        <img src="{logo}" className="wso2-logo" alt="logo" />
        <br />
        <img src="{ISLogo}" className="wso2-is-logo" alt="is_logo" /><span
          >OIDC SPA React Demo</span
        >
      </div>
      <br />
      
      <div v-if="isLoggedIn">
        <br />
        <h2>Token Response</h2>
        <div className="card access-request-block">
          <ReactJson src="{tokenResponse}" collapseStringsAfterLength="{50}" />
        </div>
        <br />
        <h2>ID Token</h2>
        <div className="card token-request-block">
          <ReactJson src="{idToken}" collapseStringsAfterLength="{50}" />
        </div>
        <br />
        <button
          className="btn btn-danger"
          v-on:click="handleLogoutBtnClick"
        >
          LOGOUT
        </button>
      </div>

      <button
        v-else
        className="btn btn-primary"
        v-on:click="handleLoginBtnClick"
      >
        LOGIN
      </button>
      
    </div>
  </div>
</template>

<script>
import { sendAuthorizationRequest, sendTokenRequest } from "../actions/sign-in";
import ReactJson from "react-json-view";
import { dispatchLogout } from "../actions/sign-out";
import {
  isValidSession,
  getAllSessionParameters,
  decodeIdToken,
} from "../actions/session";
export default {
  name: "HelloWorld",
  components: {
    ReactJson,
  },
  data() {
    return {
      idToken: {},
      tokenResponse: {},
      isLoggedIn: false,
    };
  },
  mounted() {
    this.a();
    this.b();
  },
  methods: {
    a() {
      if (isValidSession()) {
        const session = getAllSessionParameters();
        const _tokenResponse = {
          access_token: session.ACCESS_TOKEN,
          refresh_token: session.REFRESH_TOKEN,
          scope: session.SCOPE,
          id_token: session.ID_TOKEN,
          token_type: session.TOKEN_TYPE,
          expires_in: parseInt(session.EXPIRES_IN),
        };
        this.setState({
          tokenResponse: _tokenResponse,
          idToken: decodeIdToken(session.ID_TOKEN),
          isLoggedIn: true,
        });
        return;
      }
    },
    b() {
      // Reads the URL and retrieves the `code` param.
      const code = new URL(window.location.href).searchParams.get("code");

      // If a authorization code exists, sends a token request.
      if (code) {
        sendTokenRequest(code)
          .then((response) => {
            console.log("TOKEN REQUEST SUCCESS", response);
            this.setState({
              tokenResponse: response[0],
              idToken: response[1],
              isLoggedIn: true,
            });
          })
          .catch((error) => {
            console.log("TOKEN REQUEST ERROR", error);
            this.setState({ isLoggedIn: false });
          });
      }
    },
    handleLoginBtnClick() {
      sendAuthorizationRequest();
    },
    handleLogoutBtnClick() {
      dispatchLogout();
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
