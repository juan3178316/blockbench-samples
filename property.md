---
title: "Blockbench samples - Property"
description: "Get samples about how works the blockbench types documentation"
author: juan3178316
date: 2025-10-23
---

# Property Class

Creates a new property on the specified target class

## Content

```typescript
declare class Property extends Deletable {
    constructor(target_class: any, type: string, name: string, options?: PropertyOptions);
    class: any;
    name: string;
    type: string;
	default: any;
	
    isString: boolean;
    isMolang: boolean;
    isNumber: boolean;
    isBoolean: boolean;
    isArray: boolean;
    isVector: boolean;
	isVector2: boolean;
	
    merge_validation: undefined | ((value: any) => boolean);
    condition: any;
    exposed: boolean;
    label: any;
	merge: (instance: any, data: object) => void
	reset: (instance: any) => void
    getDefault(instance: any): any;
    copy(instance: any, target: any): void;
}
```

#### Parameters

+ **target_class**: _any_
+ **type**: _string_
+ **name**: _string_
+ **options?**: _[PropertyOptions](../interfaces/property-options.md)_
+ **class**: _any_
+ **default**: _any_
+ **isString**: _boolean_
+ **isMolang**: _boolean_
+ **isNumber**: _boolean_
+ **isBoolean**: _boolean_
+ **isArray**: _boolean_
+ **isVector**: _boolean_
+ **isVector2**: _boolean_