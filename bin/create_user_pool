#!/usr/bin/env node

var AWS = require('aws-sdk');

var cognitoidentityserviceprovider = new AWS.CognitoIdentityServiceProvider({ region: 'us-east-1' });
var iam = new AWS.IAM();

var params = {
  'AliasAttributes': ['email'],
  'PoolName': 'serveless_test',
};

cognitoidentityserviceprovider.createUserPool(params, function (err, poolData) {
  if (err) {
    console.error(err, err.stack);
    return;
  }

  iam.getUser({}, function (err, iamData) {
    if (err) {
      console.error(err, err.stack);
      return;
    }

    var id = iamData.User.Arn.split(':')[4];
    console.log('User Pool ARN is arn:aws:cognito-idp:us-east-1:' + id + ':userpool/' + poolData.UserPool.Id);
  });
});
