<template>
  <div id="app">
	  <header>
		  <h1>Onboarding Wizard</h1>
	  </header>
      <div>
          <table class="table">
              <tr>
                  <td><!-- ANIA TODO: move this to css -->
                      <AccordionMenu v-for="(section, i) in sections"
                                     :section="section"
                                     :index="i"
                                     :key="i"
                                     :open="section.open"
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
            open: true,
            canOpen: true
        },
        {
            header: "Primary Contact",
            content: "Content2",
            open: false,
            canOpen: false
        },
        {
            header: "Trust / Superannuation Fund Information",
            content: "Content3",
            open: false,
            canOpen: true
        },
        {
            header: "Trustee Details",
            content: "Content4",
            open: false,
            canOpen: true
        },
        {
            header: "Beneficiaries",
            content: "Content5",
            open: false,
            canOpen: true
        },
        {
            header: "Beneficial Owner(s)",
            content: "Content6",
            open: false,
            canOpen: true
        },
        {
            header: "Investment Details",
            content: "Content7",
            open: false,
            canOpen: true
        },
        {
            header: "CRS & FATCA",
            content: "Content8",
            open: false,
            canOpen: true
        },
        {
            header: "Declarations",
            content: "Content9",
            open: false,
            canOpen: true
        },
        {
            header: "Supporting Documents",
            content: "Content10",
            open: false,
            canOpen: true
        },
        {
            header: "Review and Submit",
            content: "Content11",
            open: false,
            canOpen: true
        }
      ]
    }
  },
  methods: {
    toggleOpen: function (index) {
      this.sections = this.sections.map((section, i) => {
        if (index === i && section.canOpen) {
            section.open = !section.open;
        } else {
            section.open = false;
        }

        return section;
      });
    }
  }
}
</script>
