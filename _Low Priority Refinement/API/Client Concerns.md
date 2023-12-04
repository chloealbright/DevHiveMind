---
tags: 
author:
  - jacgit18
Status: 
Started: 
EditDate: 
Relates:
---
Rule: New URIs should be used to introduce new concepts 

Rule: Schemas should be used to manage representational form versions 

Rule: Entity tags should be used to manage representational state versions 

Rule: OAuth may be used to protect resources 

Rule: API management solutions may be used to protect resources 

Rule: The query component of a URI should be used to support partial responses 

There may be times when a REST API offers a resource state model that includes a bit more data than the client wishes to receive. In order to save on bandwidth, and possibly accelerate the overall interaction, a REST API’s client can use the query component to trim response data with the fields parameter. 

The fields query parameter allows clients to request only the resource state information that it deems relevant for its particular use case. The REST API must parse the request’s query parameter’s inclusion list and return a partial response. The following example request uses the fields query parameter to request that a specific subset of data be returned for the identified student document: 

GET /students/morgan?fields=(firstName, birthDate) HTTP/1.1   

Host: api.college.restapi.org 

# Response 

HTTP/1.1 200 OK 

Content-Type: application/wrml; 

              format="http://api.formats.wrml.org/application/json"; 

              schema="http://api.schemas.wrml.org/college/Student"; 

              fields="(birthDate, firstName)"   

              fields="!(address, schedule!(friday, wednesday))"   

{ 

     "firstName" : "Morgan",   

    "birthDate" : "1992-07-31", 

    "schedule"  : { 

        "monday" : { 

            "links" : { 

                "firstClass" : { 

                    "href" : "http://api.college.restapi.org/classes/math-202", 

                    "rel"  : "http://api.relations.wrml.org/college/firstClass" 

                }, 

                # Daily schedule's other links... 

            } 

        }, 

        # Schedule's other fields (except friday and wednesday)... 

    }, 

    # Student's other fields (except address)... 

    "links" : { 

        # Student's links... 

    } 

} 

The request includes the fields parameter, which specifies the list of fields that should be included in the response’s representation. 

When the fields query parameter is used to define an inclusion list, the media type must specify a parameter, also named fields, which canonicalizes the response’s field list in case-insensitive, alphabetical order. 

The partial response contains only the firstName and birthDate fields. 

In the example above, the fields query parameter syntax indicated that the client wished to obtain the current state of two specific fields. However, sometimes it may be more convenient for the client to designate the resource state fields that it does not want to receive. For example, a client may ask an API to exclude an indicated set of fields whose values are known to be sizable and unused. 

The exclamation point character (!), which precedes the parenthetically enclosed and comma-separated names, declares a field exclusion list. 

When the fields query parameter is used to define an exclusion list, it alters the structure of the form away from its schema’s definition; thus it needs to equivalently alter the Content-Type header’s value. The media type must specify a fields parameter that lists the response’s excluded fields in case-insensitive, alphabetical order. 

The REST API’s partial response should then include all of the state representation’s fields, except those indicated in the exclusion list. 

Rule: The query component of a URI should be used to embed linked resources 

Rule: JSONP should be supported to provide multi-origin read access from JavaScript 

Rule: CORS should be supported to provide multi-origin read/write access from JavaScript