<template>
  <div class="wrapper-table" id="content-table">
        <table>
            <thead>
                <tr>
                    <th>ID</th>
                    <th>Name</th>
                    <th>Phone</th>
                    <th>Email</th>
                    <th>Pswrd</th>
                    <th>Time</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="eachRow in tabularList">
                    <td>{{eachRow.id}}</td>
                    <td>{{eachRow.name}}</td>
                    <td>{{eachRow.phone}}</td>
                    <td>{{eachRow.email}}</td>
                    <td>{{eachRow.password}}</td>
                    <td>{{eachRow.time}}</td>
                </tr>
            </tbody>
        </table>
  </div>
</template>

<script>
    export default {
        computed: {
            tabularList() {
                return this.$store.getters.tabularList;
            },
            formEnabled() {
                return this.$store.getters.formEnabled;
            }
        }
    }
</script>
<style lang="scss" scoped>
    .wrapper-table {
        display: flex;
        justify-content: center;
        margin-left: 2rem;
        margin-top: 1rem;
        table {
            width: 100%;
            border-collapse: collapse;
        }
        tr:nth-of-type(odd) {
            background: aliceblue;
        }
        th {
            background: #333;
            color: white;
            font-weight: bold;
        }
        td,
        th {
            padding: 0.5rem;
            border: 0.01rem solid #ccc;
            text-align: left;
        }
        @media only screen and (max-width: 760px),
        (min-device-width: 320px) and (max-device-width: 1025px) {
            table,
            thead,
            tbody,
            th,
            td,
            tr {
                display: block;
            }
            thead tr {
                position: absolute;
                top: -999rem;
                left: -999rem;
            }
            tr {
                border: 0.1rem solid #ccc;
            }
            td {
                border: none;
                border-bottom: 0.1rem solid #eee;
                position: relative;
                padding-left: 50%;
            }
            td:before {
                position: absolute;
                top: 0.6rem;
                left: 0.6rem;
                width: 45%;
                padding-right: 1rem;
                white-space: nowrap;
            }
            td:nth-of-type(1):before {
                content: "ID";
            }
            td:nth-of-type(2):before {
                content: "Name";
            }
            td:nth-of-type(3):before {
                content: "Phone";
            }
            td:nth-of-type(4):before {
                content: "Email";
            }
            td:nth-of-type(5):before {
                content: "Pswrd";
            }
            td:nth-of-type(6):before {
                content: "Time";
            }
        }
    }
</style>