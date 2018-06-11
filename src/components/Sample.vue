<template>
  <Page class="page">
    <ActionBar class="action-bar" title="Sample Page">
      <NavigationButton text="Go Back" android.systemIcon="ic_menu_back" @tap="$router.push('/home')"/>
    </ActionBar>

    <StackLayout class="sample">
      <Label class="body" textWrap=true text="Date Pick"/>
      <DatePicker @loaded="onDatePickerLoaded" @dateChange="onDateChanged" />
      <Button text="Button" @tap="buttonTap" />
    </StackLayout>
  </Page>
</template>
<script>
  export default {
    data () {
      return {
        text: "Form Examples"
      };
    },
    methods: {
      onDateChanged () {
        alert({
          title: "Date Changed",
          message: "The date was changed",
          okButtonText: "OK"
        }).then(() => {
          console.log("closed it");
        });
      },
      buttonTap () {
        action("Take Action", "Cancel", ["Option1", "Option2"])
          .then(result => {
            console.log(result);
          });
      }
    }
  };
</script>
<style scoped>
  .sample {
    margin: 20;
  }
</style>
