import { Client, Functions } from "packageName";

const client = new Client();

const functions = new Functions(client);

client
    .setEndpoint('https://[HOSTNAME_OR_IP]/v1') // Your API Endpoint
    .setProject('5df5acd0d48c2') // Your project ID
;

const promise = functions.createDeployment('[FUNCTION_ID]', '[ENTRYPOINT]', document.getElementById('uploader').files[0], false);

promise.then(function (response) {
    console.log(response); // Success
}, function (error) {
    console.log(error); // Failure
});