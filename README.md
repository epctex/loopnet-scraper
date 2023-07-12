[https://apify.com/epctex/loopnet-scraper](https://apify.com/epctex/loopnet-scraper?fpr=yhdrb)

# Actor - Loopnet Scraper

## Loopnet scraper

Since Loopnet doesn't provide a good and free API, this actor should help you to retrieve data from it.

The Loopnet data scraper supports the following features:

-   Search any search results - Get any search results even if it is an auction, lease, sale, or business.

-   Scrape lists by cities or regions - Retrieve data by cities, regions, or countries from Loopnet.

-   Scrape businesses for sale - Looking for businesses for sale? No worries. You can check any businesses for sale with the latest information in a blazing fast time!

-   Scrape any business or property details - Get details of properties or businesses such as location, contact information,  zones, taxes, detailed information, and many more! Just type the URL of it.

## Bugs, fixes, updates, and changelog

This scraper is under active development. If you have any feature requests you can create an issue from [here](https://github.com/epctex/loopnet-scraper/issues).


## Input Parameters

The input of this scraper should be JSON containing the list of pages on Loopnet that should be visited. Possible fields are:

- `startUrls`: (Required) (Array) List of LoopNet URLs. It should be search, list, business search, business detail, or property detail URL.

- `endPage`: (Optional) (Number) Final number of page that you want to scrape. The default is `Infinite`. This applies to all `search` requests and `startUrls` individually.

- `maxItems`: (Optional) (Number) You can limit scraped items. This should be useful when you search through the big lists or search results.

- `proxy`: (Required) (Proxy Object) Proxy configuration.

- `extendOutputFunction`: (Optional) (String) Function that takes a JQuery handle ($) as an argument and returns an object with data.

- `customMapFunction`: (Optional) (String) Function that takes each object's handle as an argument and returns the object with executing the function.

This solution requires the use of **Proxy servers**, either your own proxy servers or you can use [Apify Proxy](https://www.apify.com/docs/proxy).

### Tip

When you want to scrape over a specific listing URL, just copy and paste the link as one of the **startUrl**.

If you would like to scrape only the first page of a list then put the link for the page and have the `endPage` as 1.

With the last approach that is explained above you can also fetch any interval of pages. If you provide the 5th page of a list and define the `endPage` parameter as 6 then you'll have the 5th and 6th pages only.

### Compute Unit Consumption

The actor is optimized to run blazing fast and scrape many listings as possible. Therefore, it forefronts all listing detail requests. If the actor doesn't block very often it'll scrape 100 listings in 2 minutes with ~0.04-0.8 compute units.

### Loopnet Scraper Input example

```json
{
  "startUrls":[
    "https://www.loopnet.com/biz/new-york-businesses-for-sale/",
    "https://www.loopnet.com/biz/Business-Opportunity/six-figure-income-selling-raising-champion-ragdoll-kittens/2048785/",
    "https://www.loopnet.com/search/office-buildings/usa/for-sale/?sk=c6f67af77ac46e004033dd553ebc1429&e=u",
    "https://www.loopnet.com/Listing/701-Technology-Dr-Canonsburg-PA/27506067/",
    "https://www.loopnet.com/Listing/825-Third-Ave-New-York-NY/13877304/",
    "https://www.loopnet.com/Listing/240-Riverside-Blvd-New-York-NY/17114174/"
  ],
  "endPage":1,
  "maxItems":10,
  "proxy":{
    "useApifyProxy":true
  }
}

```

## During the Run

During the run, the actor will output messages letting you know what is going on. Each message always contains a short label specifying which page from the provided list is currently specified.
When items are loaded from the page, you should see a message about this event with a loaded item count and total item count for each page.

If you provide incorrect input to the actor, it will immediately stop with a failure state and output an explanation of what is wrong.

## Loopnet Export

During the run, the actor stores results into a dataset. Each item is a separate item in the dataset.

You can manage the results in any language (Python, PHP, Node JS/NPM). See the FAQ or <a href="https://www.apify.com/docs/api" target="blank">our API reference</a> to learn more about getting results from this Loopnet actor.

## Scraped Loopnet Output

The structure of each item in Loopnet looks like this:

### Property Detail

```json
{
    "url": "https://www.loopnet.com/Listing/3040-Sidco-Dr-Nashville-TN/26120312/",
    "type": "property",
    "title": "3040 Sidco Drive 3040 Sidco Dr",
    "offTheMarket": false,
    "subtitle": "167,954 SF Vacant Office Building Nashville, TN For Sale",
    "address": "3040 Sidco Dr, Nashville, TN 37204",
    "images": [
        "https://images1.loopnet.com/i2/HUDuSN6l9h3tb9bNoMSsowragjpjO1uuwQ_0KFIfDs0/110/3040-Sidco-Dr-Nashville-TN-3040-Sidco-Drive-Outside-Break-Area-2-Large.jpg",
        "https://images1.loopnet.com/i2/D10I9nEJM6mzYVgykYzv4aEs7yHjd9YgQeNXup5gpN0/110/3040-Sidco-Dr-Nashville-TN-3040-Sidco-Drive-3-Large.jpg",
        "https://images1.loopnet.com/i2/VP5re1ps8duZ7GFesXPy30MXzUo6dFqAO4RsoA3ZJYM/110/3040-Sidco-Dr-Nashville-TN-3040-Sidco-Drive-4-Large.jpg",
        "https://images1.loopnet.com/i2/X8sTfTUsfkAiFOAWeIcINzyopGXp3Hg1_QVcnKlh-BI/110/3040-Sidco-Dr-Nashville-TN-3040-Sidco-Drive-5-Large.jpg",
        "https://images1.loopnet.com/i2/rrrGJfzqWsSIFQkRqHqK9ML6H8Syks_YR3hk-z4J3i8/110/3040-Sidco-Dr-Nashville-TN-3040-Sidco-Drive-6-Large.jpg",
        "https://images1.loopnet.com/i2/p88q01fgwSC11JaPTbem1hcTniBe967HFCGs5jLLxgo/110/3040-Sidco-Dr-Nashville-TN-3040-Sidco-Drive-7-Large.jpg",
        "https://images1.loopnet.com/i2/kXue4FpU5lOPmGvPFZBfPTG0LdOZOEtbCcT7YSCnV7M/110/3040-Sidco-Dr-Nashville-TN-3040-Sidco-Drive-Outside-Break-Area-8-Large.jpg",
        "https://images1.loopnet.com/i2/04petxD4BDBq5Qnvp6v3fBMtoIF79dfyN-X4UW-OE9w/110/3040-Sidco-Dr-Nashville-TN-3040-Sidco-Drive-Outside-Break-Area-9-Large.jpg",
        "https://images1.loopnet.com/i2/GjCI5CvndT6a5AEKKAB_DfVMoNe8kpM9tVfJmSbNOBA/110/3040-Sidco-Dr-Nashville-TN-3040-Sidco-Drive-Break-Area-10-Large.jpg",
        "https://images1.loopnet.com/i2/jTJvP-BwDkLduLxGfnc2muK48cCVu3TsafcnwYMf9lE/110/3040-Sidco-Dr-Nashville-TN-Lobby-11-Large.jpg",
        "https://images1.loopnet.com/i2/l1iG9A62iSA5InK6FBK685eYZLvlkWjvNKOUtMqQ6qY/110/3040-Sidco-Dr-Nashville-TN-3040-Sidco-Drive-12-Large.jpg",
        "https://images1.loopnet.com/i2/psxlDt8czuHY9pblFWmKlQ6CGTiq5_zRpS_7C5-jJmI/110/3040-Sidco-Dr-Nashville-TN-3040-Sidco-Drive-13-Large.jpg",
        "https://images1.loopnet.com/i2/-SqTxXeZRtp-mgL7bo2asrflWo14b-yi_dJkJNKE0GE/110/3040-Sidco-Dr-Nashville-TN-3040-Sidco-Drive-Break-ARea-14-Large.jpg",
        "https://images1.loopnet.com/i2/04R9s2unTo9r8wp297i9QulvwIs6vt1w5oyrK7Osmyc/110/3040-Sidco-Dr-Nashville-TN-3040-Sidco-Drive-15-Large.jpg",
        "https://images1.loopnet.com/i2/61IfQxbRoetX1ADpLro3vnkD3HYl-e6UvLJ9I5a2mO8/110/3040-Sidco-Dr-Nashville-TN-3040-Sidco-Drive-Break-Area-16-Large.jpg",
        "https://images1.loopnet.com/i2/DF0eXrF1Q6nzXQ9oW2lReqJnw34dU4mh6JFk12KLb3s/110/3040-Sidco-Dr-Nashville-TN-3040-Sidco-Drive-17-Large.jpg",
        "https://images1.loopnet.com/i2/nIJmI9rSEi06x4FNluf54Tc7uZkteayrjSXBOpfkVWk/110/3040-Sidco-Dr-Nashville-TN-3040-Sidco-Drive-18-Large.jpg",
        "https://images1.loopnet.com/i2/e39Zgsu8fyoLdn4jC9EzeMC6mC-FkfuHOzdr_cKDVec/110/3040-Sidco-Dr-Nashville-TN-Patio-19-Large.jpg",
        "https://images1.loopnet.com/i2/eq6fFybJ-uKGltCcjh0O4ouiFVabT84qyH-7mDZp5N4/110/3040-Sidco-Dr-Nashville-TN-Fitness-Center-20-Large.jpg",
        "https://images1.loopnet.com/i2/Zhu0_FuS-E137eHK5KNGDuizAUhBYqKKF-ODNxNp4rs/110/3040-Sidco-Dr-Nashville-TN-3040-Sidco-Drive-Parking-21-Large.jpg",
        "https://images1.loopnet.com/i2/615I_uWoTckGJDBRjW86oF5_YXq8j_mJrlA7wI-YzyM/110/3040-Sidco-Dr-Nashville-TN-3040-Sidco-Drive-Context-22-Large.jpg",
        "https://images1.loopnet.com/i2/OG1BST245vdauIV4TQdkY59s93dJ4P8n4ypENhP8KC8/110/3040-Sidco-Dr-Nashville-TN-3040-Sidco-Drive-Birds-Eye-View-23-Large.jpg",
        "https://images1.loopnet.com/i2/0Jgt0WOeHBgRgrFybtnpVdjce_u-k-TY564AaNGBCZg/110/3040-Sidco-Dr-Nashville-TN-3040-Sidco-Drive-1-Large.jpg"
    ],
    "highlights": [
        "3040 Sidco Dr is situated minutes to downtown with convenient access to I-65, I-440, and surrounding neighborhoods.",
        "Located just outside Nashville's exploding central business district, 3040 Sidco allows commuters to reach downtown in minutes.",
        "Full amenity package, including a fitness center with locker rooms, a coffee bar, a game room, and collaborative meeting space.",
        "Four-minute drive to an abundance of retail options that include The Home Depot, Ross Dress for Less, PetSmart, T.J. Maxx, Burlington."
    ],
    "contacts": [
        {
            "name": "Morgan Hillenmeyer",
            "image": "https://images1.loopnet.com/i2/SIt60kmDuXwUXhT5VjAESTu1Y3VkNrnmnQtQOWhe_9c/106/image.jpg"
        },
        {
            "name": "Roscoe High",
            "image": "https://images1.loopnet.com/i2/lSOI8FMY8L0QJXm1lbjhl3PgSu9z61Gr8YriM1leQdU/106/image.jpg"
        }
    ],
    "contactPhone": "(629) 333-1504",
    "contactAddress": "222 2nd Ave SSuite 1800Nashville, TN 37201",
    "contactName": "CBRE, Inc.",
    "contactImage": "https://images1.loopnet.com/i2/XohiTlPxtoXlQZD7GA5pyaYFb6beVQcKcOHeRqhOcZo/105/image.png",
    "executiveSummary": "3040 Sidco offers buyers a new, adaptive reuse development ideally located in Nashville’s constantly evolving Sidco Corridor. The project transformed an existing 130,000-square-foot industrial warehouse into an approximately 160,000-square-foot high-end creative office building. 3040 Sidco provides a full range of best-in-class amenities that include a fitness center with locker rooms, a coffee bar, a game room, collaborative meeting space, and an indoor/outdoor plaza that gives employees creative space to both relax and innovate. The site also features a welcoming entrance and lobby, enhanced glass curtain and skylights, and a new parking deck for improved parking ratios, creating an inviting environment perfect for Nashville’s constantly growing labor force.  Tenants will enjoy the immediacy of retail options, including The Home Depot, Ross Dress for Less, PetSmart, T.J. Maxx, Burlington, and a Regal Hollywood movie theater, all within a four-minute drive and supplement the building’s on-site amenities. This is in addition to the menu of casual dining options within the same range, including local names and national chains, such as Jimmy John’s and Chic-fil-A. Commuting to and from the property is a breeze. It provides immediate access to I-65 and proximity to the I-440/I-65 interchange, placing it within a nine-minute drive to Nashville’s central business district. 3040 Sidco Drive presents a modernized asset that provides a high-end experience featuring a host of top-end amenities in reach of Downtown Nashville.",
    "attachments": [],
    "amenities": [],
    "transportation": [
        {
            "location": "Riverfront Commuter Rail (East Corridor Line)",
            "travelTime": "9 min drive\n\t\t\t\t\t\t\t\t\t\t\t5.4 mi",
            "distance": "9 min drive"
        },
        {
            "location": "Donelson Commuter Rail (East Corridor Line)",
            "travelTime": "13 min drive\n\t\t\t\t\t\t\t\t\t\t\t9.4 mi",
            "distance": "13 min drive"
        },
        {
            "location": "Nashville International Airport",
            "travelTime": "13 min drive\n\t\t\t\t\t\t\t\t\t\t\t7.1 mi",
            "distance": "13 min drive"
        }
    ],
    "nearbyAmenities": [],
    "zoning": [],
    "propertyTaxes": [
        {
            "key": "Parcel Number",
            "value": "132-04-0-010"
        },
        {
            "key": "Land Assessment",
            "value": "$860,400"
        }
    ],
    "auction": {
        "currentBid": "",
        "bidIncrement": "",
        "nextBid": "",
        "inProgress": ""
    }
}
```

### Business Detail

```json
{
    "url": "https://www.loopnet.com/biz/Business-Opportunity/six-figure-income-selling-raising-champion-ragdoll-kittens/2048785/",
    "type": "business",
    "title": "Six figure income selling/raising Champion Ragdoll Kittens",
    "region": "Wading River, NY",
    "pricing": [
        {
            "key": "Asking Price",
            "value": "$49,975"
        },
        {
            "key": "Gross Revenue",
            "value": "$175,000"
        },
        {
            "key": "Established Year",
            "value": "2013"
        },
        {
            "key": "Cash Flow",
            "value": "$125,000"
        },
        {
            "key": "Inventory",
            "value": "$27,000"
        }
    ],
    "description": "Rewarding Career in Kitty Sales and Holistic Pet Food We are an internationally recognized and award winning cattery since 2013.  Family owned and operated.  We have mentored three successful sister catteries and are needing to open three more in the next 90 days to meet demands of client inquiries for Ragdoll Cats and Kittens, the NUMBER ONE feline breed nationwide since December of 2020.  Sister Catteries are needed in Massachusetts/Connecticut/New Jersey. Turn key system, six figure income potential the first year, full hands on mentoring and advertising support from home cattery. Flexible schedule, work from home, multiple streams of income.  Enjoy a rewarding career that has a positive impact on your community.",
    "documents": [
        "https://www.loopnet.com/biz/images/shared/listings/204/2048785/ac0f3127-57fd-4cc1-82fb-9a1d666228d2.pdf"
    ],
    "details": [
        {
            "key": "Location",
            "value": "Wading River, NY"
        },
        {
            "key": "Inventory",
            "value": "Included in asking price"
        },
        {
            "key": "Employees",
            "value": "6"
        },
        {
            "key": "Facilities",
            "value": "1 stud and 3 dams for sister cattery.  All nursery materials needed for first season.  Start up inventory for holistic pet food sales. Business cards and brochures.  Advertising package included."
        },
        {
            "key": "Competition",
            "value": "Ragdolls cats and kittens are in high demand.  Catteries are sold out and not able to meet the client inquires to purchase these wonderful cats.  Holistic pet food is a billion dollar annual sales market.  Convenience of holistic pet food with direct shipping saves clients time and money providing increased health and longevity for their beloved pets."
        },
        {
            "key": "Growth & Expansion",
            "value": "Growth opportunity after first successful season.  We have a proven system in place to annually increase income.  Kitten sales and Pet food sales alone can be well over six figures annually."
        },
        {
            "key": "Support & Training",
            "value": "Hands on mentoring, advertising support for first season, client referral program, website design, internet commerce website included for 90 days for exclusive holistic pet food line.   Web portal for pet food sales.   Direct shipping from manufacturer to client, no inventory needed."
        },
        {
            "key": "Reason for Selling",
            "value": "We are expanding to meet the HIGH demand for Champion Ragdoll Cats and Kittens."
        },
        {
            "key": "Home-Based",
            "value": "This business is Home-Based"
        }
    ],
    "contact": {
        "name": "Claire Michaels",
        "phone": "631-830-9300"
    }
}
```

## Contact
Please visit us through [epctex.com](https://epctex.com) to see all the products that are available for you. If you are looking for any custom integration or so, please reach out to us through the chat box in [epctex.com](https://epctex.com). In need of support? [devops@epctex.com](mailto:devops@epctex.com) is at your service.
