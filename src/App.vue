<template>
  <div id="app">
    <Header></Header>
    <AppContainer>

      <SectionIntro></SectionIntro>
      <SectionBusyWork></SectionBusyWork>
      <SectionFileShare></SectionFileShare>
      <SectionLearnMore></SectionLearnMore>
      <SectionDropBoxPlans></SectionDropBoxPlans>
      <Footer></Footer>
      <Form></Form>

    </AppContainer>
  </div>
</template>

<script>
import AppContainer from './components/Container.vue'
import Header from './components/Header.vue'
import SectionIntro from './components/SectionIntro.vue'
import SectionBusyWork from './components/SectionBusyWork.vue'
import SectionFileShare from './components/SectionFileShare.vue'
import SectionLearnMore from './components/SectionLearnMore.vue'
import SectionDropBoxPlans from './components/SectionDropBoxPlans.vue'
import Footer from './components/Footer.vue'
import Form from './components/Form.vue'

export default {
  name: 'App',
  components: {
    AppContainer,
    Header,
    SectionIntro,
    SectionBusyWork,
    SectionFileShare,
    SectionLearnMore,
    SectionDropBoxPlans,
    Footer,
    Form
  }
}
</script>
