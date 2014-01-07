WebService-EchoNest
===================

## NAME

WebService::EchoNest - A simple Perl interface to the EchoNest API

## SYNOPSIS

```perl
my $echonest = WebService::EchoNest->new(
    api_key    => 'XXX',
);

my $data = $echonest->request('artist/search',
  name   => 'Radiohead',
  bucket => ['biographies'],
  limit  => 'true'
);
```

## DESCRIPTION

The module provides a simple interface to the EchoNest API. To use this module, you must first sign up at http://developer.echonest.com/ to receive an API key.

You can then make requests on the API. You pass in a method name and hash of paramters, and a data structure mirroring the response is returned.

This module confesses if there is an error.

## METHODS

####request

This makes a request:
```pelr
my $data = $echonest->request('artist/search',
  name   => 'Black Moth Super Rainbow',
  bucket => ['images'],
  limit  => 'true'
);
```

####create_http_request

If you want to integrate this module into another HTTP framework, this method will create an HTTP::Request object:
```perl
my $http_request = $echonest->create_http_request('artist/search',
  name   => 'Black Moth Super Rainbow',
  bucket => ['images'],
  limit  => 'true'
);
```

##AUTHOR

Nick Langridge <nickl@cpan.org>

##CREDITS

This module was based on Net::LastFM by Leon Brocard.

##COPYRIGHT

Copyright (C) 2013 Nick Langridge

##LICENSE

This module is free software; you can redistribute it or modify it under the same terms as Perl itself.
