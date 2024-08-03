# scrapr-core-interfaces

> *scrapr-core-interfaces* will provide shared interfaces for the *scrapr-core\** packages.

## Contents

- [Description](#description)
- [Interfaces](#interfaces)
    - [IScraprCore](#iscraprcore)
    - [IScraprCoreSearch](#iscraprcoresearch)
    - [IScraprCoreSearchInput](#iscraprcoresearchinput)
    - [IScraprCoreSearchInputCookies](#iscraprcoresearchinputcookies) - TBC
    - [IScraprCoreSearchInputHistory](#iscraprcoresearchinputhistory)
    - [IScraprCoreSearchOutput](#iscraprcoresearchoutput) - TBC
    - [IScraprCoreFormatter](#iscraprcoreformatter)
    - [IScraprCoreFormatterFormat](#iscraprcoreformatterformat)
    - [IScraprCoreFormatterFormatInput](#iscraprcoreformatterformatinput)
    - [IScraprCoreFormatterFormatOutput](#iscraprcoreformatterformatoutput)
    - [IScraprCoreRequester](#iscraprcorerequester)
    - [IScraprCoreRequesterRequest](#iscraprcorerequesterrequest)
    - [IScraprCoreRequesterRequestInput](#iscraprcorerequesterrequestinput)
    - [IScraprCoreRequesterRequestOutput](#iscraprcorerequesterrequestoutput)
    - IScraprCoreScraper
    - IScraprCoreScraperScrape
    - IScraprCoreScraperScrapeInput
    - IScraprCoreScraperScrapeOutput
    - IScraprCoreService
    - IScraprCoreServiceSearch
    - IScraprCoreServiceSearchInput
    - IScraprCoreServiceSearchOutput
    - IScraprCoreServiceParser
    - IScraprCoreServiceParserParse
    - IScraprCoreServiceParserParseInput
    - IScraprCoreServiceParserParseOutput
    - IScraprCoreServiceRegistry
    - IScraprCoreServiceRegistryGetService
    - IScraprCoreServiceRegistryGetServiceInput
    - IScraprCoreServiceRegistryGetServiceOutput
- [Enaums](#enums)
    - [ScraprCoreFeaturesEnum](#scraprcorefeaturesenum)
    - [ScraprCoreFormatEnum](#scraprcoreformatenum)
    - [ScraprCoreLanguageEnum](#scraprcorelanguageenum)
    - [ScraprCoreRegionEnum](#scraprcoreregionenum)
- [TBC](#tbc)
    - [IScraprCoreSearchInputCookies](#iscraprcoresearchinputcookies)
    - [IScraprCoreSearchOutput](#iscraprcoresearchoutput)
    - [IScraprCoreRequesterRequestOutput](#iscraprcorerequesterrequestoutput)

## Description


## Interfaces

### IScraprCore

```TypeScript
import { IScraprCoreSearch } from "./IScraprCoreSearch";

export interface IScraprCore {
    search: IScraprCoreSearch;
};
```

### IScraprCoreSearch

```TypeScript
import { IScraprCoreSearchInput } from "./IScraprCoreSearchInput";
import { IScraprCoreSearchOutput } from "./IScraprCoreSearchOutput";

export interface IScraprCoreSearch {
    (params: IScraprCoreSearchInput): IScraprCoreSearchOutput;
};
```

### IScraprCoreSearchInput

```TypeScript
export interface IScraprCoreSearchInput {
    cookies: IScraprCoreSearchInputCookies;
    features: ScraprCoreFeaturesEnum;
    format: ScraprCoreFormatEnum;
    history:  IScraprCoreSearchInputHistory;
    language: ScraprCoreLanguageEnum;
    region: ScraprCoreRegionsEnum;
    searchTerm: string;

};
```

### IScraprCoreSearchInputCookies

TBC

```TypeScript
export interface IScraprCoreSearchInputCookies {};
```

### IScraprCoreSearchInputHistory

```TypeScript
export type IScraprCoreSearchInputHistory = string[];
```

### IScraprCoreSearchOutput

TBC

```TypeScript
export type IScraprCoreSearchOutput = {

};
```

### IScraprCoreFormatter

```TypeScript
import { IScraprCoreFormatterFormat } from "./IScraprCoreFormatterFormat";

export interface IScraprCoreFormatter {
    format: IScraprCoreFormatterFormat;
}
```

### IScraprCoreFormatterFormat

```TypeScript
import { IScraprCoreFormatterFormatInput } from "./IScraprCoreFormatterFormatInput";
import { IScraprCoreFormatterFormatOutput } from "./IScraprCoreFormatterFormatOutput";

export interface IScraprCoreFormatterFormat {
    ({ params }: IScraprCoreFormatterFormatInput): IScraprCoreFormatterFormatOutput

}
```

### IScraprCoreFormatterFormatInput

```TypeScript
import { IScraprCoreSearchInput } from "./IScraprCoreSearchInput";

export type IScraprCoreFormatterFormatInput = IScraprCoreSearchInput;
```

### IScraprCoreFormatterFormatOutput

```TypeScript
import { IScraprCoreSearchInput } from "./IScraprCoreSearchInput";

export type IScraprCoreFormatterFormatOutput = IScraprCoreSearchInput;
```

### IScraprCoreRequester

```TypeScript
import { IScraprCoreRequesterRequest } from "./IScraprCoreRequesterRequest";

export interface IScraprCoreRequester {
    request: IScraprCoreRequesterRequest;
}
```

### IScraprCoreRequesterRequest

```TypeScript
import { IScraprCoreRequesterRequestInput } from "./IScraprCoreRequesterRequestInput";
import { IScraprCoreRequesterRequestOutput } from "./IScraprCoreRequesterRequestOutput";

export interface IScraprCoreRequesterRequest {
    ({ params }: IScraprCoreRequesterRequestInput): IScraprCoreRequesterRequestOutput;
}
```

### IScraprCoreRequesterRequestInput

```TypeScript

export type IScraprCoreRequesterRequestInput = IScraprCoreSearchInput;
```

### IScraprCoreRequesterRequestOutput

```TypeScript

TBC

export interface IScraprCoreRequesterRequestOutput {}
```

## Enums

### ScraprCoreFeaturesEnum

```TypeScript
enum ScraprCoreFeaturesEnum {
  IMAGE = 1,
  ORGANIC = 2,
  PERSON = 3
  SHOPPING = 4
  RECOMMENDED = 5
}
```

### ScraprCoreFormatEnum

```TypeScript
enum ScraprCoreFormatEnum {
  JSON = 1,
  TXT = 2,
  XML = 3
}
```

### ScraprCoreLanguageEnum

```TypeScript
enum ScraprCoreLanguageEnum {
  EN = 1,
  ES = 2,
  ...
}
```

### ScraprCoreRegionEnum

```TypeScript
enum ScraprCoreRegionEnum {
  EU_1 = 1,
  EU_2 = 2,
  ...
}
```

## TBC

- [IScraprCoreSearchInputCookies](#iscraprcoresearchinputcookies)
- [IScraprCoreSearchOutput](#iscraprcoresearchoutput)
- [IScraprCoreRequesterRequestOutput](#iscraprcorerequesterrequestoutput)
