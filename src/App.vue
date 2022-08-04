<template>
  <div id="app">
	  <header>
		  <h1>Onboarding Wizard</h1>
	  </header>
      <div class="faqs">
          <table class="table">
              <tr>
                  <td><!-- ANIA TODO: move this to css -->
                      <AccordionMenu v-for="(faq, i) in sections"
                                     :faq="faq"
                                     :index="i"
                                     :key="i"
                                     :open="faq.open"
                                     @toggleOpen="toggleOpen" />
                  </td>
                  <td>
                      <div class="container">
                          Main Content
                      </div>
                  </td>
              </tr>
          </table>
      </div>
  </div>
</template>

<script>
    import AccordionMenu from './AccordionMenu';
    require('./page.css');
    // Ania TODO Add expandable prop: bool to sections //

export default {
  name: 'app',
  components: {
      AccordionMenu
  },
  data () {
    return {
      sections: [
        {
          header: "Start Application",
          content: "Content1",
          open: true
        },
        {
          header: "Primary Contact",
          content: "Content2",
          open: false
        },
        {
          header: "Trust / Superannuation Fund Information",
          content: "Content3",
          open: false
        },
        {
            header: "Trustee Details",
            content: "Content4",
            open: false
        },
        {
            header: "Beneficiaries",
            content: "Content5",
            open: false
        },
        {
            header: "Beneficial Owner(s)",
            content: "Content6",
            open: false
        },
        {
            header: "Investment Details",
            content: "Content7",
            open: false
        },
        {
            header: "CRS & FATCA",
            content: "Content8",
            open: false
        },
        {
            header: "Declarations",
            content: "Content9",
            open: false
        },
        {
            header: "Supporting Documents",
            content: "Content10",
            open: false
        },
        {
            header: "Review and Submit",
            content: "Content11",
            open: false
        }
      ]
    }
  },
  methods: {
    toggleOpen: function (index) {
      this.sections = this.sections.map((faq, i) => {
        if (index === i) {
          faq.open = !faq.open;
        } else {
          faq.open = false;
        }

        return faq;
      });
    }
  }
}
</script>
