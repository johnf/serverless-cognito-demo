#!/usr/bin/env node

var AWS = require('aws-sdk');

var cognitoidentityserviceprovider = new AWS.CognitoIdentityServiceProvider({ region: 'us-east-1' });

var params = {
  'UserPoolId': process.argv[2],
};

cognitoidentityserviceprovider.deleteUserPool(params, function (err) {
  if (err) {
    console.error(err, err.stack);
    return;
  }

  console.log('Deleted pool');
});
