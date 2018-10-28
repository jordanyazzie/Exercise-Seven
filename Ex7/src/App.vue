<template>
    <div class="container">
        <form>
            <div class="row" v-if=!isSubmitted>
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
            <!-- Part 1 5 Points-->
            <!-- Create a Signup Form where you retrieve the following Information -->
                    <h1>Sign Up</h1>
            <!-- Full Name (First Name + Last Name) -->
                    <div class="form-group">
                        <label for="firstName">First Name</label>
                        <input
                                type="text"
                                id="firstName"
                                class="form-control"
                                v-model="signUp.firstName">
                    </div>
                    <div class="form-group">
                        <label for="lastName">Last Name</label>
                        <input
                                type="text"
                                id="lastName"
                                class="form-control"
                                v-model="signUp.lastName">
                    </div>

            <!-- Mail -->
                    <div class="form-group">
                        <label for="email">Mail</label>
                        <input
                                type="email"
                                id="email"
                                class="form-control"
                                v-model="signUp.email">
                    </div>
            <!-- Password -->
                    <div class="form-group">
                        <label for="password">Password</label>
                        <input
                                type="password"
                                id="password"
                                class="form-control"
                                v-model="signUp.password">
                    </div>
            <!-- Store Data? Yes/No -->
                    <div class="row">
                        <div class="form-group">
                            <label>Store Data?</label>
                            <label for="Yes">
                                <input
                                        type="radio"
                                        id="Yes"
                                        value="Yes"
                                        v-model="signUp.storeData"> Yes
                            </label>
                            <label for="No">
                                <input
                                        type="radio"
                                        id="No"
                                        value="No"
                                        v-model="signUp.storeData"> No
                            </label>
                        </div>
                    </div>

            <!-- Part 2 5 Points -->
            <!-- Only display the Form if it has NOT been submitted -->
            <!-- Display the Data Summary ONCE the Form HAS been submitted -->
                    <div class="row">
                            <button
                                    class="btn btn-primary"
                                    @click.prevent="submitted">Submit!
                            </button>
                    </div>

                    <!-- Part 3 5 Points -->
                    <!-- Edit the Example from above and create a custom "Full Name" Control -->
                    <!-- which still holds the First Name and Last Name Input Field -->

                </div>
            </div>
        </form>
        <hr>
        <div class="row" v-if="isSubmitted">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <div class="panel panel-default">
                    <div class="panel-heading">
                        <h4>Your Data</h4>
                    </div>
                    <div class="panel-body">
                        <p>Full Name:{{signUp.firstName}} {{signUp.lastName}} </p>
                        <p>Mail: {{signUp.email}}</p>
                        <p>Password: {{signUp.password}}</p>
                        <p>Store in Database?: {{signUp.storeData}}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data () {
            return {
                signUp: {
                    email: '',
                    password: '',
                    firstName: '',
                    lastName: '',
                    storeData: ''
                },
                isSubmitted: false
            }
        },
        methods: {
            submitted() {
                this.isSubmitted = true;
            }
        }
    }
</script>

<style>
</style>
