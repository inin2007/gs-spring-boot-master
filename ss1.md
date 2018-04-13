@jsontest
Feature: JSON Test Services

  Scenario: IP Address
    Given Server is accessible
    When I access ip.jsontest.com
    Then Server returns my IP Address in JSON Format

  Scenario: Headers
    Given  Server is accessible
    When I access  headers.jsontest.com
    Then I got my headers in JSON format.
    And  "Host" header value should be "headers.jsontest.com"

  Scenario: Date&Time
    Given  Server is accessible
    When I access  www.jsontest.com/#date
    Then I got my Date&Time in JSON format.
    And  "Date"  value should be Todays date

  Scenario: Echo
    Given  Server is accessible
    When I access  www.jsontest.com/#echo
    Then I got the Echo in JSON format.
    And  "one"  value should be "two"



  Scenario: Arbitrary JS Code

    Given  Server is accessible
    When I access  code.jsontest.com
    Then I got the Alert in JSON format.
    And  "validate"  the IP address value should be correct

  Scenario: Cookie

    Given  Server is accessible
    When I access  cookie.jsontest.com
    Then I got the cookie status.
    And  "cookie_status"  value should be "Cookie set with name jsontestdotcom"

  Scenario: MD5

    Given  Server is accessible
    When I access  md5.jsontest.com/?text=[text to MD5]
    Then I got the MD5 hash code.
    And  "original"  value should be text value sent 

