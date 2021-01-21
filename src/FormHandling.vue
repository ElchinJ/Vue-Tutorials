<template>
    <form>
        <div>
            <pre>
                {{JSON.stringify(formValues, null, 2)}}
            </pre>
        </div>
        <div>
            <label for="name">Name is: </label>
            <br>
            <input type="text" id="name" v-model="formValues.name">
        </div>

        <div>
            <label for="profile">Profile summary:</label>
            <br>
            <textarea id="profile" cols="30" rows="10" v-model="formValues.profileSummary"/>
        </div>
        <hr>

        <div>
            <label for="country">Country</label>
            <br>
            <select id="country" v-model="formValues.country">
                <option value="">Select country</option>
                <option value="India">India</option>
                <option value="Germany">Germany</option>
                <option value="Argentina">Argentina</option>
            </select>
        </div>
        <hr>

        <div>
            <label for="job-location">Job location:</label>
            <br>
            <select id="job-location" multiple v-model="formValues.jobLocation">
                <option value="India">India</option>
                <option value="Germany">Germany</option>
                <option value="Argentina">Argentina</option>
            </select>
        </div>
    </form>
</template>

<script>
    export default {
        name: 'formHandling',
        data() {
            return {
                formValues: {
                    name: '',
                    profileSummary: '',
                    country: '',
                    jobLocation: [],
                }
            }
        },
    }
</script>

<style lang="scss" scoped>

</style>