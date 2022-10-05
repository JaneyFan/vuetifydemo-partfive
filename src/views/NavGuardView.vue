<template>
    <div v-if="isLoggedin">
        only show if user is logged in 

        <h1>Hello {{user.email}}</h1> 
            
        <h1>Hello splitted name{{userNameOnly}}</h1> 

    </div>
    <div v-else>
        only show if user is not logged in
    </div>
 
    
</template>

<script setup>
import {onMounted} from 'vue';   
import useUsers from '@/modules/useUsers';
const {isLoggedin, isLoggedinTest, user} = useUsers();
import {computed} from 'vue';   

/* import useUsers from '@/modules/useUsers';
const {logOut} = useUsers(); */
/* const user =localStorage.getItem('userLoginInfoFireBase'); */
/* import {onMounted} from 'vue';

import useUsers from '@/modules/useUsers'; */

/* const {isLoggedin, isLoggedIntest} = useUsers();

let auth
const isLoggedin = ref(false)

onMounted(() => {
  isLoggedIntest()
  });


 */
 onMounted(() => {
  isLoggedinTest()
  });

  const userNameOnly = computed (() => {
    return user.value.email.split('@')[0]
  })

</script>


