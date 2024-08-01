# scrapr-core

## Description

- This package will provide the public entry point to the *scrapr-core* collection of packages.
- It will be a library that will enable SERP data to be scraped and returned in real time.
- It will be used within the *scrapr-api* package.

## Classes

- ScraprCore
- ParamFilter
- ParamValidater

## Class methods

- **ScraprCore.search**(args: IScraprCoreSearchInput): *IScraprCoreSearchOutput* (static) [PUBLIC]
- **ParamFilter.filter**(args: IScraprCoreSearchInput): *IScraprCoreSearchInput* (static) [PRIVATE]
- **ParamValidater.parse**(args: IScraprCoreSearchInput): *void* (static) [PRIVATE]

## Dependencies
- scrapr-core-formatter
- scrapr-core-interfaces
- scrapr-core-service-registry

## Pseudo code

```TypeScript
import { ParamFilter } from "./ParamFilter";
import { ParamValidater } from "./ParamValidater";
import { ScraprCoreFormatter } from "datr-tech/scrapr-core-formatter";
import { ScraprCoreServiceRegistry } from "datr-tech/scrapr-core-service-registry";
import { IScraprCore, IScraprCoreSearchInput, IScraprCoreSearchOutput } from "datr-tech/scrapr-core-interfaces";

export class ScraprCore: IScraprCore {
  /**
   * @params {IScraprCoreSearchInput} params
   * @return IScraprCoreSearchOutput[]
   */
  public static search(...params:  IScraprCoreSearchInput): IScraprCoreSearchOutput[] {
    ParamValidater.validate(params);
    
    const paramsFiltered = ParamFilter.filter(params);
    const { formatId, serviceIds } = paramsFiltered;
    const searchResults: IScraprCoreSearchOutput[] = [];

    for (let serviceId in serviceIds) {
        let service = ScraprCoreServiceRegistry.getService(serviceId);
        let searchResultsPerService = service.search(paramsFiltered);
        let searchResultsPerServiceFormatted = ScraprCoreFormatter.format(formatId, seviceOutput)
        
        searchResults.push(searchResultsPerServiceFormatted);
    }

    return searchResults;
  }
}

```