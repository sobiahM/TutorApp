<script>
  import { alert } from "@nativescript/core";
  export let tutorName;

  const unAvail = () => {
    alert("Feature not implemented");
  };
</script>

<page backgroundImage="~/image/img.jpg">
  <actionBar title="Welcome {tutorName}" />
  <flexboxLayout
    alignContent="center"
    justifyContent="center"
    flexDirection="column"
  >
    <button on:tap={unAvail} text="Find Student" />
    <button on:tap={unAvail} text="Chat with Student" />
    <button on:tap={unAvail} text="Student List" />
    <button on:tap={unAvail} text="Schedule Class" />
    <button on:tap={unAvail} text="Edit Profile" />
  </flexboxLayout>
</page>
