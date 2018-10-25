<template>
    <div class="container">
        <form v-if="!submitted">
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <h1>Signup Form</h1>
                    <hr>
                    <div class="form-group">
                    <label for="firstName">First Name</label>
                    <input type="text"
                           id="firstName"
                           class="form-control"
                            v-model="userData.firstName">
                </div>
                <div class="form-group">
                    <label for="lastName">Last Name</label>
                    <input type="text"
                           id="lastName"
                           class="form-control"
                           v-model="userData.lastName">
                </div>
                <div class="form-group">
                    <label for="email">Email</label>
                    <input type="text"
                           id="email"
                            class="form-control"
                           v-model="userData.email">
                </div>
                <div class="form-group">
                    <label for="password">Password</label>
                    <input type="password"
                           id="password"
                           class="form-control"
                           v-model="userData.password">
                </div>

                <div class="row">
                    <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3 form-group">
                        <p>Would you like to store your data?</p>
                        <label for="yes">
                            <input
                                    type="radio"
                                    id="yes"
                                    value="Yes"
                                    v-model="storeData"
                                    > Yes
                        </label>
                        <label for="no">
                            <input
                                    type="radio"
                                    id="no"
                                    value="No"
                                    v-model="storeData"
                                    > No
                        </label>
                    </div>
                </div>
                <div class="row">
                    <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                        <button type="submit"
                            class="button"
                                @click.prevent="submitted = true"
                            >Submit!
                        </button>
                    </div>
                </div>

                    <!-- Part 1 5 Points-->
                    <!-- Create a Signup Form where you retrieve the following Information -->
                    <!-- Full Name (First Name + Last Name) -->
                    <!-- Mail -->
                    <!-- Password -->
                    <!-- Store Data? Yes/No -->

                    <!-- Part 2 5 Points -->
                    <!-- Only display the Form if it has NOT been submitted -->
                    <!-- Display the Data Summary ONCE the Form HAS been submitted -->

                    <!-- Part 3 5 Points -->
                    <!-- Edit the Example from above and create a custom "Full Name" Control -->
                    <!-- which still holds the First Name and Last Name Input Field combine first and last name-->
                </div>
            </div>
        </form>
        <hr>
        <div class="row" v-if="submitted">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <div class="panel panel-default">
                    <div class="panel-heading">
                        <h4>Your Data</h4>
                    </div>
                    <div class="panel-body">
                        <p>Full Name: {{userData.firstName}} {{userData.lastName}}</p>
                        <p>Mail: {{userData.email}}</p>
                        <p>Password: {{userData.password}} </p>
                        <p>Store in Database?: {{storeData}}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
      data(){
        return{
          userData: {
            firstName: '',
            lastName: '',
            email: '',
            password: ''
          },
          storeData: 'Yes',
          submitted: false
        }
        }
    }
</script>

<style>
</style>
