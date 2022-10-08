<script>
  import { alert } from "@nativescript/core";
  import { navigate } from "svelte-native";
  import Tutor from "./Tutor.svelte";
  import User from "./User.svelte";

  let userName, userPass;
  let tutorName, tutorPass;

  var users = {
    Ash: 1803,
  };
  var tutors = {
    Sofi: 1803,
  };

  const onUserLogin = () => {
    if (!(userName in users)) {
      alert("User Not Found");
    } else if (users[userName] != userPass) {
      alert("Wrong Password");
    } else {
      navigate({
        page: User,
        props: {
          userName: userName,
        },
      });
    }
  };

  const onTutorLogin = () => {
    if (!(tutorName in tutors)) {
      alert("Tutor Not Found");
    } else if (tutors[tutorName] != tutorPass) {
      alert("Wrong Password");
    } else {
      navigate({
        page: Tutor,
        props: {
          tutorName: tutorName,
        },
      });
    }
  };
</script>

<page backgroundImage="~/image/img.jpg">
  <actionBar title="Tutor App" />
  <tabView>
    <tabViewItem title="STUDENT">
      <flexboxLayout
        alignContent="center"
        justifyContent="center"
        flexDirection="column"
      >
        <textField
          bind:text={userName}
          hint="USERNAME"
          textAlignment="center"
          style.placeholderColor="white"
          color="white"
        />
        <textField
          bind:text={userPass}
          hint="Password"
          textAlignment="center"
          style.placeholderColor="white"
          color="white"
          secure="true"
        />
        <button on:tap={onUserLogin} text="LOGIN" />
        <button text="REGISTER" />
      </flexboxLayout>
    </tabViewItem>
    <tabViewItem title="TUTOR">
      <flexboxLayout
        alignContent="center"
        justifyContent="center"
        flexDirection="column"
      >
        <textField
          bind:text={tutorName}
          hint="UserName"
          textAlignment="center"
          style.placeholderColor="white"
          color="white"
        />
        <textField
          bind:text={tutorPass}
          hint="Password"
          textAlignment="center"
          style.placeholderColor="white"
          color="white"
          secure="true"
        />
        <button on:tap={onTutorLogin} text="LOGIN" />
        <button text="REGISTER" />
      </flexboxLayout>
    </tabViewItem>
  </tabView>
</page>
