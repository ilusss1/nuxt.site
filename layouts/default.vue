<script setup>
import logo from "@/assets/l.png"

useHead({
  script: [
    {
      hid: 'ga4',
      innerHTML: `(function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
      (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
      m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
      })(window,document,'script','https://www.google-analytics.com/analytics.js','ga');
      ga('create', 'G-9V8HLP0WQQ', 'auto');
      ga('send', 'pageview');`,
      type: 'text/javascript'
    }
  ],
  __dangerouslyDisableSanitizersByTagID: {
    'ga4': ['innerHTML']
  }
})
</script>

