## Medics API v1.0
|        	|          	    |      	|
|--------	|----------	|---	|
| **`Endpoint`** 			| To be provided |
| **`Method`** 				| POST|
| **`Path`**  					| /v1^tkapi | 
| **`Resources`**  			| Demographics and Userforms | 

### Sample POST Body
```
{
	"api_key": "tobeprovided",
	
	"demographics": {
		"ads_account_number": "100/1",
		"medical_record_number": "ABCD123",
		"ar_class_code": "SP",
		"language": "English",
		"ethnicity": "Not Hispanic",
		"race": "Asian",
		"relationship_to_guarantor": "Dependent",

		"patient": {
			"last_name": "GREGORY",
			"first_name": "HOUSE",
			"middle_initial": "M",
			"dob": "19591106",
			"sex": "M",
			"address_1": "123 MAIN ST",
			"address_2": "APT 2",
			"city": "PARAMUS",
			"state": "NJ",
			"zip": "07652",
			"social_security_number": "444444444",
			"home_phone": "8888888888",
			"email": "test@adsc.com",
			"cell_phone": "8888888888",
			"work_phone": "8888888888"
		},
		
		"guarantor": {
			"last_name": "BAR",
			"first_name": "SARA",
			"middle_initial": "",
			"dob": "19951006",
			"sex": "F",
			"address_1": "123 MAIN ST",
			"address_2": "APT 1",
			"city": "PARAMUS",
			"state": "NJ",
			"zip": "07652",
			"social_security_number": "555555555",
			"home_phone": "2013682001",
			"email": "test2@adsc.com",
			"cell_phone": "2013682001",
			"work_phone": ""
		},
		
		"insurance": {
			"primary": {
				"holder": "Guarantor",
				"code": "NYBS",
				"description": "NEW YORK BLUESHIELD",
				"policy": "12223334444A",
				"group_id": "",
				"insured_relation_to_patient": "",
				"insured_last_name": "",
				"insured_first_name": "",
				"insured_dob": "",
				"insured_address": "",
				"insured_city": "",
				"insured_state": "",
				"insured_zip": ""
			},
			
			"secondary": {
				"holder": "",
				"code": "",
				"description": "",
				"policy": "",
				"group_id": "",
				"insured_relation_to_patient": "",
				"insured_last_name": "",
				"insured_first_name": "",
				"insured_dob": "",
				"insured_address": "",
				"insured_city": "",
				"insured_state": "",
				"insured_zip": ""
			}
		}
	},
	
	"userforms": {
		"sforce": {
			"P1": "Lookup",
			"P2": "Radiobutton",
			"P3": "Lookup",
			"P4": "Date",
			"P5": "Date",
			"P6": "Lookup",
			"P7": "Radiobutton",
			"P8": "Text",
			"P9": "Radiobutton",
			"P10": "Radiobutton",
			"P11": "Radiobutton",
			"P12": "Lookup",
			"P13": "Text",
			"P14": "Lookup",
			"P15": "Text",
			"P16": "Lookup",
			"P17": "Text",
			"P18": "Radiobutton",
			"P19": "Text",
			"P20": "Text",
			"P21": "Decimal",
			"P22": "Radiobutton",
			"P23": "Radiobutton",
			"P24": "Radiobutton",
			"P25": "Radiobutton",
			"P26": "Text",
			"P27": "Text",
			"P28": "Radiobutton",
			"P29": "Text",
			"P30": "Radiobutton",
			"P31": "Radiobutton",
			"P32": "Date",
			"P43": "Text",
			"P44": "Text",
			"P45": "Text",
			"P46": "Text",
			"P47": "Lookup",
			"P48": "Lookup",
			"P49": "Radiobutton",
			"P50": "Text",
			"P51": "Text",
			"P52": "Text",
			"P53": "Text",
			"P54": "Text",
			"P55": "Text",
			"P56": "Date",
			"P57": "Text",
			"P58": "Text",
			"P60": "Radiobutton",
			"P61": "Text",
			"P62": "Text",
			"P63": "Radiobutton",
			"P64": "Radiobutton",
			"P65": "Radiobutton",
			"P66": "Radiobutton",
			"P67": "Text",
			"P68": "Text",
			"P69": "Radiobutton",
			"P70": "Date",
			"P71": "Date",
			"P72": "Text",
			"P73": "Radiobutton",
			"P74": "Radiobutton",
			"P75": "Radiobutton",
			"P76": "Text"
		}
	}
}
```
### POST Body Details
| Root | Type 	| Comment 	| Required?  	|
|------------------------------------	|--------------	|------------------------------------------------------------------	|------------|
| `api_key` 	&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| Alphanumeric 	| Will be assigned a key for production, and a key for testing  	|  Yes |

***
| demographics | Type 	| Comment 	| Required?  	|
|------------------------------------	|--------------	|------------------------------------------------------------------	|------------|
| `ads_account_number` 	| Numeric 	| a `/` is optional to denote the patient number: 100, 100/1 |No 	|
| `medical_record_number` 	| Alphanumeric 	|  	| No 	|
| `ar_class_code`| Alphanumeric 	| Medics Premier AR class code. if none is provided, a default AR class will be assigned. | No |
| `language`| Alphanumeric 	| If a code match is found, it will be used, otherwise a match will be attempted based on description. | No |
| `ethnicity`| Alphanumeric 	|If a code match is found, it will be used, otherwise a match will be attempted based on description.  | No |
| `race`| Alphanumeric 	| If a code match is found, it will be used, otherwise a match will be attempted based on description. | No |
| `relationship_to_guarantor`| Enum| Possible Values: `Self` `Spouse` `Dependent` `Child` `Other`  | No |

***

| demographics.patient | Type 	| Comment 	| Required?  	|
|------------------------------------	|--------------	|------------------------------------------------------------------	|------------|
| `last_name` 	| Alpha |  |Yes|
| `first_name` 	| Alpha |  |Yes|
| `middle_initial` 	| Alpha | Max Length=1 |No|
| `dob` 	| Numeric | YYYYMMDD |Yes|
| `sex` 	| Enum |`M` or `F`  |Yes|
| `address_1` 	| Alphanumeric |  |No 	|
| `address_2` 	| Alphanumeric |  |No 	|
| `city` 	| Alpha  |  |No 	|
| `state` 	| Alpha | Max length=2| No 	|
| `zip` 	| Numeric | Max length=10 |No 	|
| `social_security_number` 	| Numeric | Max Length=9 |No 	|
| `home_phone` 	| Numeric | Max length=10 |No 	|
| `email` 	| Alphanumeric  |  |No 	|
| `cell_phone` 	| Numeric |  |No 	|
| `work_phone` 	| Numeric | Max length=14The format is 8008994237 2020. Phone number and extension separated by a space. |No 	|


***


| demographics.guarantor| Type 	| Comment 	| Required?  	|
|------------------------------------	|--------------	|------------------------------------------------------------------	|------------|
| `last_name` 	| Alpha |  |If relationship to guarantor is not `Self` |
| `first_name` 	| Alpha |  |If relationship to guarantor is not `Self`|
| `middle_initial` 	| Alpha | Max Length=1 |No|
| `dob` 	| Numeric | YYYYMMDD |If relationship to guarantor is not `Self`|
| `sex` 	| Enum |`M` or `F` | If relationship to guarantor is not `Self`|
| `address_1` 	| Alphanumeric |  |No 	|
| `address_2` 	| Alphanumeric |  |No 	|
| `city` 	| Alpha  |  |No 	|
| `state` 	| Alpha | Max length=2| No 	|
| `zip` 	| Numeric | Max length=10 |No 	|
| `social_security_number` 	| Numeric | Max Length=9 |No 	|
| `home_phone` 	| Numeric | Max length=10 |No 	|
| `email` 	| Alphanumeric  |  |No 	|
| `cell_phone` 	| Numeric |  |No 	|
| `work_phone` 	| Numeric | Max length=14The format is 8008994237 2020. Phone number and extension separated by a space. |No 	|

***


| insurance.primary| Type 	| Comment 	| Required?  	|
|------------------------------------	|--------------	|------------------------------------------------------------------	|------------|
| `holder` 	| Enum | Possible values: `Guarantor` or `Other`   | Yes |
| `code` 	| Alphanumeric | Medics Premier Insurance Code | No|
| `description` 	| Alphanumeric | If code is not provided, a match will be attempted based on description. If neither is provided, insurance will be skipped  |No |
| `policy` 	| Alphanumeric|  | |
| `group_id` 	| Alphanumeric|  | |
| `insured_relation_to_patient` 	| Enum| Possible values: `Self` `Child` `Spouse` `Dependent` `Other` | If `holder` is not `Guarantor` |
| `insured_last_name` 	| Alpha |  | If `holder` is `Other`|
| `insured_first_name` 	| Alpha |  | If `holder` is `Other`|
| `insured_dob` 	| Alpha |  | If `holder` is `Other`|
| `insured_address` 	| Alpha |  | If `holder` is `Other`|
| `insured_city` 	| Alpha |  | If `holder` is `Other`|
| `insured_state` 	| Alpha |  | If `holder` is `Other`|
| `insured_zip` 	| Alpha |  | If `holder` is `Other`|

***


| insurance.secondary| Type 	| Comment 	| Required?  	|
|------------------------------------	|--------------	|------------------------------------------------------------------	|------------|
| `holder` 	| Enum | Possible values: `Guarantor` or `Other`   | Yes |
| `code` 	| Alphanumeric | Medics Premier Insurance Code | No|
| `description` 	| Alphanumeric | If code is not provided, a match will be attempted based on description. If neither is provided, insurance will be skipped  |No |
| `policy` 	| Alphanumeric|  | |
| `group_id` 	| Alphanumeric|  | |
| `insured_relation_to_patient` 	| Enum| Possible values: `Self` `Child` `Spouse` `Dependent` `Other` | If `holder` is not `Guarantor` |
| `insured_last_name` 	| Alpha |  | If `holder` is `Other`|
| `insured_first_name` 	| Alpha |  | If `holder` is `Other`|
| `insured_dob` 	| Alpha |  | If `holder` is `Other`|
| `insured_address` 	| Alpha |  | If `holder` is `Other`|
| `insured_city` 	| Alpha |  | If `holder` is `Other`|
| `insured_state` 	| Alpha |  | If `holder` is `Other`|
| `insured_zip` 	| Alpha |  | If `holder` is `Other`|

***

> **Userform DataTypes:**

> - `Lookup` : a match will attempted based on code, if not found, a match based on description will be attempted, otherwise, a new entry will be added based on the value provided. 
> - `Radiobutton`:  Enum of integers from 1 to 8. If a different value is provided, a match will be attempted based on the description of the radio buttons. 
> - `Date`:  YYYYMMDD



***
| userforms.sforce| Type 	| Comment 	| Required?  	|
|------------------------------------	|--------------	|------------------------------------------------------------------	|------------|
	|`P1`|Lookup|       MARKETING REP | No |
	|`P2`|Radiobutton|       CLIENT TYPE | No |
	|`P3`|Lookup|       OPPORUNITY STAGE | No |
	|`P4`|Date |       VOB CREATED | No |
	|`P5`|Date |       CLOSE DATE | No |
	|`P6`|Lookup|       LEAD SOURCE | No |
	|`P7`|Radiobutton|       PATIENT HAS INSURANCE | No |
	|`P8`|Text|       MEMBER SERVICE # | No |
	|`P9`|Radiobutton|       MEDICAL COMPLICATIONS | No |
	|`P10`|Radiobutton|       LEGAL COMPLICATIONS | No |
	|`P11`|Radiobutton|       PREVIOUS TREATMENT | No |
	|`P12`|Lookup|       SUBSTANCES OF ABUSE # 1 | No |
	|`P13`|Text|       SUB #1 AMOUNT | No |
	|`P14`|Lookup|       SUB #2 | No |
	|`P15`|Text|       SUB #2 AMOUNT | No |
	|`P16`|Lookup|       SUB #3 | No |
	|`P17`|Text|       SUB #3 AMOUNT | No |
	|`P18`|Radiobutton|       IS CLIENT A STUDENT | No |
	|`P19`|Text|       FAMILY CONTACT FIRST NAME | No |
	|`P20`|Text|       FAMILY CONTACT LAST NAME | No |
	|`P21`|Numeric|       CLIENT AGE | No |
	|`P22`|Radiobutton|       VOB STATUS | No | 
	|`P23`|Radiobutton|       SUICIDE ATTEMPTS | No |
	|`P24`|Radiobutton|       MENTAL ILLNESS | No |
	|`P25`|Radiobutton|       SELF HARM | No |
	|`P26`|Text|       HEIGHT/WT | No |
	|`P27`|Text|       CURRENT MEDS | No |
	|`P28`|Radiobutton|       ALLERGIES | No |
	|`P29`|Text|       OTHER HEALTH ISSUES | No |
	|`P30`|Radiobutton|       PRIOR ARRESTS | No |
	|`P31`|Radiobutton|       ON PROBATION | No |
	|`P32`|Date |       PENDING COURT DATE | No |
	|`P43`|Text|       EMAIL ADDRESS PATIENT | No |
	|`P44`|Text|       EMAIL ADDRESS PARENT | No |
	|`P45`|Text|       PARENT PHONE # | No |
	|`P46`|Text|       EMERGENCY CONTACT PHONE # | No |
	|`P47`|Lookup|       PRIMARY INSURANCE | No |
	|`P48`|Lookup|       PROGRAM | No |
	|`P49`|Radiobutton|       PRE ADMIT STATUS | No | 
	|`P50`|Text|       COMMENTS | No |
	|`P51`|Text|       PATIENT NAME | No |
	|`P52`|Text|       ADDRESS | No |
	|`P53`|Text|       PHONE | No |
	|`P54`|Text|       OTHER PHONE | No |
	|`P55`|Text|       EMAIL | No |
	|`P56`|Date |       DOB | No |
	|`P57`|Text|       AGE | No |
	|`P58`|Text|       SSN | No |
	|`P60`|Radiobutton|       HALLUCINATIONS | No |
	|`P61`|Text|       HEIGHT | No |
	|`P62`|Text|       WEIGHT | No |
	|`P63`|Radiobutton|       GANG AFFILIATION | No |
	|`P64`|Radiobutton|       PERMISSION TO TRAVEL | No |
	|`P65`|Radiobutton|       CANCER | No |
	|`P66`|Radiobutton|       SEIZURES | No |
	|`P67`|Text|       OTHER COMMENTS | No |
	|`P68`|Text|       INSURANCE TYPE | No | 
	|`P69`|Radiobutton|       IS POLICY ACTIVE| No |
	|`P70`|Date |       POLICY EFFECTIVE DATE| No |
	|`P71`|Date |       TERM DATE ON POLICY| No |
	|`P72`|Text|       LICENSE REQUIREMENTS| No |
	|`P73`|Radiobutton|       IS THIS PRIMARY OR SECONDARY| No |
	|`P74`|Radiobutton|       FREE STANDING FACILITIES ALLOWED| No |
	|`P75`|Radiobutton|       IS THIS A UNION POLICY| No |
	|`P76`|Text|       STATE OF PLAN| No |
