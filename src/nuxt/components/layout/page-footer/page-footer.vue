<template>
  <footer class="footer-container">
    <div class="footer-wrapper">
      <a class="between">
        <switch-theme :size="'18px'"></switch-theme>
        <span class="logo">Bruce</span>
      </a>
      <div class="menu-wrapper">
        <desktop-nav :navList="navList"></desktop-nav>
      </div>
      <div class="social-links between">
        <a href="mailto:brusw@outlook.com">
          <i class="icon icon-mail"></i>
        </a>
        <a href="https://github.com/brusw" target="_blank">
          <i class="icon icon-github"></i>
        </a>
      </div>
    </div>
    <div class="footer-copyright">
      <span class="copyright">© {{currentYear}} <span class="logo"><a href="https://brucewei.com" target="_blank">Bruce</a></span></span>. All Right Reserved.
    </div>
  </footer>
</template>

<script>
import SwitchTheme from '@/components/base/switch-theme/switch-theme'
import DesktopNav from '@/components/base/nav/desktop-nav'

export default {
  components: {
    SwitchTheme,
    DesktopNav
  },

  props: {
    navList: {
      type: Array,
      default: () => []
    }
  },

  computed: {
    currentYear() {
      return (new Date()).getFullYear()
    }
  }
}
</script>

<style lang="scss" scoped>
.footer-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 100%;
  z-index: $index-normal;

  .footer-wrapper {
    box-sizing: border-box;
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: calc(100% - 85px - 85px);
    max-width: 1024px;
    margin-top: 8vh;
    padding: 0 15px 15px;

    @media (max-width: 1399px) {
      max-width: 950px;
    }

    @media (max-width: 1023px) {
      flex-direction: column;
    }

    @media (max-width: 479px) {
      width: 100%;
    }

    .menu-wrapper {
      @media (max-width: 1023px) {
        margin: 14px 0;
      }
    }

    .between {
      width: 100px;

      @media (max-width: 1023px) {
        display: flex;
        justify-content: center;
      }
    }

    .logo {
      margin-left: 8px;
      line-height: 1.8;
    }

    .social-links {
      display: flex;
      justify-content: flex-end;
      font-size: 1rem;

      @media (max-width: 1023px) {
        justify-content: center;
      }

      a {
        display: flex;
        align-items: center;
        margin-left: 24px;

        &:first-child {
          margin-left: 0;
        }
      }

      .icon {
        font-size: $font-size-icon-rem;

        &:hover {
          color: var(--theme-active);
        }
      }

      .text {
        white-space: nowrap;

        &:hover {
          color: var(--theme-active);
        }
      }
    }
  }

  .footer-copyright {
    font-size: 12px;
    font-weight: 400;
    line-height: 1.3;
    max-width: 600px;
    margin: 0 auto;
    padding: 25px 30px;
    text-align: center;
    letter-spacing: .7px;
    color: var(--font-color-light);

    .copyright {
      font-weight: $font-weight-bold;

      .logo {
        color: var(--font-color-dark);
      }
    }
  }
}

.record-number {
  margin-top: 10px;
};
</style>
