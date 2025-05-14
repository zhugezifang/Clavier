<style lang="less">
@pblue: #1296db;
.page-footer { width: 100%; min-width: 1024px; height: 50px; line-height: 50px; background: rgba(255,255,255,0.5); position: absolute; width: 100%; bottom: 0; left: 0; right: 0; text-align: center;
  a {
    &:hover { color: #fff; background: @pblue; }
  }
  .record-info { font-weight: bold; font-size: 14px; }
  .footer-ul { height: 100%; position: absolute; right: 5%; top: 0;
    .footer-item { display: inline; list-style: none; position: relative; }
  }
  .support-container { width: 200px; height: 250px; position: absolute; top: -280px; left: 50%; transform: translateX(-60%); z-index: 200; background: rgba(255, 255, 255, 1);
    &::after { content: ''; width: 20px; height: 20px; position: absolute;  left: 50%; bottom: -10px; transform: translateX(-50%) rotate(45deg); z-index: 150; background: rgba(255, 255, 255, 1); }
    .tab-wrap { width: 100%; height: 60px;
      .tab { width: 50%; height: 100%; float: left; cursor: pointer;
        &.active-tab { border-bottom: solid 5px @pblue; }
        .icon { transform: scale(.5); transform-origin: 50% 0; margin-top: 14px; }
      }
    }
    .qrcode-wrap { width: 100%; padding: 12px 18px;
      .qrcode { width: 100%; }
    }
  }
}
</style>


<h3>What is a Virtual Piano?</h3>
<p>A Virtual Piano is an online tool that allows you to play piano right from your computer or mobile device. You can use your keyboard to play notes, just like a real piano. It's a fun way to create music and practice without needing a physical piano!
</p>

<h3>Can I access the Virtual Piano from anywhere?</h3>
<p>Yes, you can access the Virtual Piano from anywhere in the world. If you're not in mainland China, you can use our mirror website for faster access. Just open the link and start playing!
</p>

<h3>How do I play notes on the Virtual Piano?</h3>
<p>You can play notes using the keyboard on your device! Each key on your keyboard corresponds to a note on the piano. For example, if you press the 'A' key, it will produce the note 'La'. Have fun exploring different notes and creating your own music!
</p>

<h3>Do I need any special equipment to use the Virtual Piano?</h3>
No special equipment is needed! You can use your computer or mobile device with a standard keyboard. However, if you have a MIDI keyboard, you can connect it to your device for an even better experience.

<h3>Is it free to use the Virtual Piano?<h3>
Yes, playing the Virtual Piano is completely free! You can play anytime you want, without any charges. Just visit the website, and you're ready to go!

</h3>What if my browser doesn't support the Virtual Piano?<h3>
If your browser doesn't support the Virtual Piano, we recommend using Google Chrome or Opera, as they work best with our platform. Make sure to update to the latest version for the best experience!

<h3>Can I create my own music sheets?<h3>
Absolutely! You can create your own music sheets using our tool. Just visit the 'Create Music Sheet' section on our website and follow the steps to compose your own music.

<h3>Is there a mobile app for the Virtual Piano?</h3>
Yes, there is a mobile app for the Virtual Piano! You can scan the QR codes provided on the website to download the app on your mobile device and play piano on the go.

<h3>What types of instruments can I use with the Virtual Piano?<h3>
The Virtual Piano offers a variety of instrument sounds. You can choose from pianos, guitars, and even unique sounds like music boxes or xylophones! Try them out to see which sounds you like best.

<h3>Can beginners use the Virtual Piano?</h3>
Yes, beginners can easily use the Virtual Piano! The design is simple and user-friendly, making it perfect for anyone who wants to learn and have fun playing music.


<template>
  <div class="page-footer">
    <a href="https://www.suncreativesolution.com/#/project/clavier" target="_blank" class="record-info">By Sun</a>
    <a href="https://github.com/WarpPrism/AutoPiano" class="record-info">&copy;Script credit: 晶体世界</a>
    <ul class="footer-ul">
      <!--<li class="footer-item"><a href="//crystalworld.xin/apple/#/iphone_music" target="_blank">iPhone Music Player</a></li>-->
      <li class="footer-item"></li>
      <li class="footer-item">
        <div class="support-container" v-show="supportShow">
          <div class="tab-wrap">
            <div class="tab" :class="{'active-tab': payType=='WXPAY'}" @click="togglePayType('WXPAY')">
              <i class="icon icon-wxpay"></i>
            </div>
            <div class="tab" :class="{'active-tab': payType=='ALIPAY'}" @click="togglePayType('ALIPAY')">
              <i class="icon icon-alipay"></i>
            </div>
          </div>
        </div>
      </li>
    </ul>


  </div>
</template>

<script>
export default {
  name: 'PageFooter',
  data() {
    return {
      supportShow: false,
      payType: 'ALIPAY'
    }
  },
  methods: {
    togglePayType (type) {
      this.payType = type
    },
    toggleSupportShow() {
      this.supportShow = !this.supportShow
    }
  }
}
</script>
