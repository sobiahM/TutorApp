<script>
  import { alert } from "@nativescript/core";
  export let userName;

  const unAvail = () => {
    alert("Feature not implemented");
  };
</script>

<page backgroundImage="~/image/img.jpg">
  <actionBar title="Welcome {userName}" />
  <flexboxLayout
    alignContent="center"
    justifyContent="center"
    flexDirection="column"
  >
    <button on:tap={unAvail} text="Find Tutor" />
    <button on:tap={unAvail} text="Chat with Tutotr" />
    <button on:tap={unAvail} text="Tutor List" />
    <button on:tap={unAvail} text="Schedule's" />
    <button on:tap={unAvail} text="Edit Profile" />
  </flexboxLayout>
</page>
