# Servarr Documentation

In this document there's all the settings to get Radarr, Sonarr, Bazarr and Sabnzbd working together.


# Radarr

## Media Management

### Movie Naming

 - [x] Rename Movies
 - [x] Replace Illigal Characters
 - Colon Replacement = Delete
 - Standard Movie Format: `{Movie CleanTitle} {(Release Year)} {imdb-{ImdbId}} {[Custom Formats]}{[Quality Full]}{[MediaInfo 3D]}{[MediaInfo VideoDynamicRangeType]}{[Mediainfo AudioCodec}{ Mediainfo AudioChannels}][{Mediainfo VideoCodec}]`
	 
 - Movie Folder Format: `{Movie Title} ({Release Year})`
 
### Importing
 
 - [x] Use Hardlinks instead of Copy

## Profiles

### Any
#### Qualities
 - [x] Raw-HD

### Ultra-HD High
#### Qualities
 - [x] Remux-2160p
 - [x] Blueray-2160p
#### Custom Format

| ||
|--|--|
|  TrueHD ATMOS | 5000 |
|  DTS X | 4500 |
|  ATMOS (undefined) | 3000 |
|  DD+ ATMOS| 3000|
| TrueHD | 2750 |
| DTS-HD MA | 2500 |
| FLAC | 2250 |
| PCM | 2250 |
| DTS-HD HRA | 2000 |
| DD+ | 1750 |
| DTS-ES | 1500 |
| NO DV | 1500 |
| DTS | 1250 |
| AAC | 1000 |
| HDR10+ BOOST | 901 |
| DD | 750 |
| HDR10+ | 600 |
| HDR | 500 |
| HDR (undefined) | 500 |
| HDR10 | 500 |
| HLG | 500 |
| PQ | 500 |
| 3D | -10000 |
| BR-DISK | -10000 |
| DV (WEBDL) | -10000 |
| DV HDR10 | -10000 |
| DV HLG | -10000 |
| DV SDR | -10000 |
| x265 (HD) | -10000 |

### Ultra-HD Low
#### Qualities
 - [x] Blueray-2160p
 - [x] WEB 2160p
#### Custom Format

| ||
|--|--|
|  TrueHD ATMOS | 5000 |
|  DTS X | 4500 |
|  ATMOS (undefined) | 3000 |
|  DD+ ATMOS| 3000|
| TrueHD | 2750 |
| DTS-HD MA | 2500 |
| FLAC | 2250 |
| PCM | 2250 |
| DTS-HD HRA | 2000 |
| DD+ | 1750 |
| DTS-ES | 1500 |
| NO DV | 1500 |
| DTS | 1250 |
| AAC | 1000 |
| HDR10+ BOOST | 901 |
| DD | 750 |
| HDR10+ | 600 |
| HDR | 500 |
| HDR (undefined) | 500 |
| HDR10 | 500 |
| HLG | 500 |
| PQ | 500 |
| 3D | -10000 |
| BR-DISK | -10000 |
| DV (WEBDL) | -10000 |
| DV HDR10 | -10000 |
| DV HLG | -10000 |
| DV SDR | -10000 |
| x265 (HD) | -10000 |


## Profiles
| Quality|Min|Preferred|Max| 
|--|--|--|--|
| Unknown | 0 | 399 | 1 |
| WORKPRINT | 0 | 399 | 1 |
| CAM | 0 | 399 | 1 |
| TELESYNC | 0 | 399 | 1 |
| TELECINE | 0 | 399 | 1 |
| REGIONAL | 0 | 399 | 1 |
| DVDSCR | 0 | 399 | 1 |
| SDTV | 0 | 399 | 1 |
| DVD | 0 | 399 | 1 |
| DVD-R | 0 | 399 | 1 |
| WEBDL-480p | 0 | 399 | 1 |
| WEBRip-480p | 0 | 399 | 1 |
| Bluray-480p | 0 | 399 | 1 |
| Bluray-576p | 0 | 399 | 1 |
| HDTV-720p | 0 | 399 | 1 |
| WEBDL-720p | 0 | 399 | 1 |
| WEBRip-720p | 0 | 399 | 1 |
| Bluray-720p | 0 | 399 | 1 |
| HDTV-1080p | 33.8 |95 | 100 |
| WEBDL-1080p | 12.5 |95 | 100 |
| WEBRip-1080p | 12.5 |95 | 100 |
| Bluray-1080p | 50.8 | 399 | 400 |
| Remux-1080p | 136.8 |399 | 400 |
| HDTV-2160p | 85 | 399 | 400 |
| WEBDL-2160p | 34.5 | 399 | 400 |
| WEBRip-2160p | 34.5 | 399 | 400 |
| Bluray-2160p | 102 | 399 | 400 |
| Remux-2160p | 187.4 | 399 | 400 |
| BR-DISK | 0 | 399 | 400 |
| Raw-HD | 0 | 399 | 400 |

## Custom Formats
- 3D
   

>      {
>           "name": "3D",
>           "includeCustomFormatWhenRenaming": false,
>           "specifications": [
>             {
>               "name": "3D",
>               "implementation": "ReleaseTitleSpecification",
>               "negate": false,
>               "required": false,
>               "fields": {
>                 "value": "\\b3d|sbs|half[ .-]ou|half[ .-]sbs\\b"
>               }
>             },
>             {
>               "name": "BluRay3D",
>               "implementation": "ReleaseTitleSpecification",
>               "negate": false,
>               "required": false,
>               "fields": {
>                 "value": "\\b(BluRay3D)\\b"
>               }
>             }
>           ]
>         }

- AAC






> {
>       "name": "AAC",
>       "includeCustomFormatWhenRenaming": false,
>       "specifications": [
>         {
>           "name": "AAC",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": false,
>           "required": true,
>           "fields": {
>             "value": "\\bAAC(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not DTS",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bDTS(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not Dolby Digital Plus ",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bDD[P+]|\\b(e[-_. ]?ac3)\\b"
>           }
>         },
>         {
>           "name": "Not Basic Dolby Digital",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bDD[^a-z+]|(?<!e)ac3"
>           }
>         },
>         {
>           "name": "Not PCM",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(l?)PCM(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not FLAC",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bFLAC(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not TrueHD/ATMOS",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "True[ .-]?HD|\\bATMOS(\\b|\\d)"
>           }
>         }
>       ]
>     }

    
- ATMOS (undefined)

  

     

>   {
>       "name": "ATMOS (undefined)",
>       "includeCustomFormatWhenRenaming": false,
>       "specifications": [
>         {
>           "name": "ATMOS",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": false,
>           "required": true,
>           "fields": {
>             "value": "\\bATMOS(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not AAC",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bAAC(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not Basic Dolby Digital ",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bDD[^a-z+]|(?<!e)ac3"
>           }
>         },
>         {
>           "name": "Not Dolby Digital Plus",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bDD[P+]|\\b(e[-_. ]?ac3)\\b"
>           }
>         },
>         {
>           "name": "Not DTS",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bDTS(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not FLAC",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bFLAC(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not PCM",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(l?)PCM(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not RlsGrp (Atmos Only)",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "W4NK3R|HQMUX"
>           }
>         },
>         {
>           "name": "Not TrueHD",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "True[ .-]?HD"
>           }
>         }
>       ]
>     }

- BR-DISK

   

>  {
>       "name": "BR-DISK",
>       "includeCustomFormatWhenRenaming": false,
>       "specifications": [
>         {
>           "name": "BR-DISK",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": false,
>           "required": true,
>           "fields": {
>             "value": "^(?!.*\\b((?<!HD[._ -]|HD)DVD|BDRip|MKV|XviD|WMV|d3g|BDREMUX|REMUX|^(?=.*1080p)(?=.*HEVC)|[xh][-_.
> ]?26[45]|German.*DL|((?<=\\d{4}).*German.*(DL)?)(?=.*\\b(AVC|HEVC|VC[-_.
> ]?1|MVC|MPEG[-_. ]?2)\\b))\\b)(((?=.*\\b(Blu[-_. ]?ray|BD|HD[-_.
> ]?DVD)\\b)(?=.*\\b(AVC|HEVC|VC[-_. ]?1|MVC|MPEG[-_.
> ]?2|BDMV|ISO)\\b))|^((?=.*\\b(^((?=.*\\b((.*_)?COMPLETE.*|Dis[ck])\\b)(?=.*(Blu[-_.
> ]?ray|HD[-_. ]?DVD)))|3D[-_. ]?BD|BR[-_. ]?DISK|Full[-_. ]?Blu[-_.
> ]?ray|^((?=.*((BD|UHD)[-_. ]?(25|50|66|100|ISO)))))))).*"
>           }
>         }
>       ]
>     }

- DD

   

>  {
>       "name": "DD",
>       "includeCustomFormatWhenRenaming": false,
>       "specifications": [
>         {
>           "name": "Basic Dolby Digital",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": false,
>           "required": true,
>           "fields": {
>             "value": "\\bDD[^a-z+]|(?<!e)ac3"
>           }
>         },
>         {
>           "name": "Not Dolby Digital Plus",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bDD[P+]|\\b(e[-_. ]?ac3)\\b"
>           }
>         },
>         {
>           "name": "Not TrueHD/ATMOS",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "True[ .-]?HD|\\bATMOS(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not DTS",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bDTS(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not FLAC",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bFLAC(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not AAC",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bAAC(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not PCM",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(l?)PCM(\\b|\\d)"
>           }
>         }
>       ]
>     }

- DD+

   

>  {
>       "name": "DD+",
>       "includeCustomFormatWhenRenaming": false,
>       "specifications": [
>         {
>           "name": "Dolby Digital Plus",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": false,
>           "required": true,
>           "fields": {
>             "value": "\\bDD[P+](?!A)|\\b(e[-_. ]?ac3)\\b"
>           }
>         },
>         {
>           "name": "Not TrueHD/ATMOS",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "True[ .-]?HD|\\bATMOS(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not DTS",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bDTS(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not FLAC",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bFLAC(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not AAC",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bAAC(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not PCM",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(l?)PCM(\\b|\\d)"
>           }
>         }
>       ]
>     }

- DD+ ATMOS

   

>  {
>       "name": "DD+ ATMOS",
>       "includeCustomFormatWhenRenaming": false,
>       "specifications": [
>         {
>           "name": "Dolby Digital Plus",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": false,
>           "required": true,
>           "fields": {
>             "value": "\\bDD[P+]|\\b(e[-_. ]?ac3)\\b"
>           }
>         },
>         {
>           "name": "ATMOS",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": false,
>           "required": true,
>           "fields": {
>             "value": "\\b(ATMOS|DDPA)(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not TrueHD",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "True[ .-]?HD"
>           }
>         },
>         {
>           "name": "Not DTS",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bDTS(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not Basic Dolby Digital ",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bDD[^a-z+]|(?<!e)ac3"
>           }
>         },
>         {
>           "name": "Not FLAC",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bFLAC(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not AAC",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bAAC(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not PCM",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(l?)PCM(\\b|\\d)"
>           }
>         }
>       ]
>     }
- DTS

   

>  {
>       "name": "DTS",
>       "includeCustomFormatWhenRenaming": false,
>       "specifications": [
>         {
>           "name": "Basic DTS",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": false,
>           "required": true,
>           "fields": {
>             "value": "\\bDTS(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not DTS-HD",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(dts[-_. ]?(ma|hd([-_. ]?ma)?|xll))\\b"
>           }
>         },
>         {
>           "name": "Not DTS-HD HRA/ES",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "dts[-. ]?(es|(hd[. ]?)?(hr|hi))"
>           }
>         },
>         {
>           "name": "Not Dolby Digital Plus",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bDD[P+]|\\b(e[-_. ]?ac3)\\b"
>           }
>         },
>         {
>           "name": "Not TrueHD/ATMOS",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "True[ .-]?HD|\\bATMOS(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not Basic Dolby Digital",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bDD[^a-z+]|(?<!e)ac3"
>           }
>         },
>         {
>           "name": "Not DTS X",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(dts[-_. ]?x)\\b(?!\\d)"
>           }
>         },
>         {
>           "name": "Not FLAC",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bFLAC(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not AAC",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bAAC(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not PCM",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(l?)PCM(\\b|\\d)"
>           }
>         }
>       ]
>     }
- DTS X
> 
>     {
>       "name": "DTS X",
>       "includeCustomFormatWhenRenaming": false,
>       "specifications": [
>         {
>           "name": "DTS X",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": false,
>           "required": true,
>           "fields": {
>             "value": "\\b(dts[-_. ]?x)\\b(?!\\d)"
>           }
>         },
>         {
>           "name": "Not Basic DTS",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "DTS[ .]?[1-9]"
>           }
>         },
>         {
>           "name": "Not Basic Dolby Digital",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bDD[^a-z+]|(?<!e)ac3"
>           }
>         },
>         {
>           "name": "Not Dolby Digital Plus",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bDD[P+]|\\b(e[-_. ]?ac3)\\b"
>           }
>         },
>         {
>           "name": "Not TrueHD/ATMOS",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "True[ .-]?HD|\\bATMOS(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not FLAC",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bFLAC(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not AAC",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bAAC(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not PCM",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(l?)PCM(\\b|\\d)"
>           }
>         }
>       ]
>     }

- DTS-ES

   

>  {
>       "name": "DTS-ES",
>       "includeCustomFormatWhenRenaming": false,
>       "specifications": [
>         {
>           "name": "DTS-ES",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": false,
>           "required": true,
>           "fields": {
>             "value": "dts[-. ]?es\\b"
>           }
>         },
>         {
>           "name": "Not TrueHD/ATMOS",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "True[ .-]?HD|\\bATMOS(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not Dolby Digital Plus",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bDD[P+]|\\b(e[-_. ]?ac3)\\b"
>           }
>         },
>         {
>           "name": "Not Basic DTS",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "DTS[ .]?[1-9]"
>           }
>         },
>         {
>           "name": "Not Basic Dolby Digital ",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bDD[^a-z+]|(?<!e)ac3"
>           }
>         },
>         {
>           "name": "Not DTS X",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(dts[-_. ]?x)\\b(?!\\d)"
>           }
>         },
>         {
>           "name": "Not FLAC",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bFLAC(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not AAC",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bAAC(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not PCM",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(l?)PCM(\\b|\\d)"
>           }
>         }
>       ]
>     }
 - DTS-HD HRA
> 
>     {
>       "name": "DTS-HD HRA",
>       "includeCustomFormatWhenRenaming": false,
>       "specifications": [
>         {
>           "name": "DTS-HD HRA",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": false,
>           "required": true,
>           "fields": {
>             "value": "dts[-. ]?(hd[. ]?)?(hra?|hi\\b)"
>           }
>         },
>         {
>           "name": "Not TrueHD/ATMOS",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "True[ .-]?HD|\\bATMOS(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not Dolby Digital Plus",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bDD[P+]|\\b(e[-_. ]?ac3)\\b"
>           }
>         },
>         {
>           "name": "Not Basic DTS",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "DTS[ .]?[1-9]"
>           }
>         },
>         {
>           "name": "Not Basic Dolby Digital ",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bDD[^a-z+]|(?<!e)ac3"
>           }
>         },
>         {
>           "name": "Not DTS X",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(dts[-_. ]?x)\\b(?!\\d)"
>           }
>         },
>         {
>           "name": "Not FLAC",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bFLAC(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not AAC",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bAAC(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not PCM",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(l?)PCM(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not DTS-ES",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "dts.?es"
>           }
>         },
>         {
>           "name": "Not 6.1 Surround",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "[^0-9]6[ .][0-1]"
>           }
>         }
>       ]
>     }

- DTS-HD MA

   

>  {
>       "name": "DTS-HD MA",
>       "includeCustomFormatWhenRenaming": false,
>       "specifications": [
>         {
>           "name": "DTS-HD MA",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": false,
>           "required": true,
>           "fields": {
>             "value": "\\b(dts[-_. ]?(ma|hd([-_. ]?ma)?|xll))\\b"
>           }
>         },
>         {
>           "name": "Not TrueHD/ATMOS",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "True[ .-]?HD|\\bATMOS(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not Dolby Digital Plus",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bDD[P+]|\\b(e[-_. ]?ac3)\\b"
>           }
>         },
>         {
>           "name": "Not Basic Dolby Digital ",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bDD[^a-z+]|(?<!e)ac3"
>           }
>         },
>         {
>           "name": "Not DTS X",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(dts[-_. ]?x)\\b(?!\\d)"
>           }
>         },
>         {
>           "name": "Not FLAC",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bFLAC(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not AAC",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bAAC(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not PCM",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(l?)PCM(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not DTS-HD HRA/ES",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "dts[-. ]?(es|(hd[. ]?)?(hr|hi))"
>           }
>         }
>       ]
>     }
> - DV (WEBDL)
> 
>     {
>       "name": "DV (WEBDL)",
>       "includeCustomFormatWhenRenaming": false,
>       "specifications": [
>         {
>           "name": "Dolby Vision",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": false,
>           "required": true,
>           "fields": {
>             "value": "\\b(dv|dovi|dolby[ .]?vision)\\b"
>           }
>         },
>         {
>           "name": "WEBDL",
>           "implementation": "SourceSpecification",
>           "negate": false,
>           "required": false,
>           "fields": {
>             "value": 7
>           }
>         },
>         {
>           "name": "WEBRIP",
>           "implementation": "SourceSpecification",
>           "negate": false,
>           "required": false,
>           "fields": {
>             "value": 8
>           }
>         },
>         {
>           "name": "Not RlsGrp",
>           "implementation": "ReleaseGroupSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(Flights)\\b"
>           }
>         },
>         {
>           "name": "Not HDR",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bHDR(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not Hulu",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(hulu)\\b"
>           }
>         }
>       ]
>     }

- DV HDR10

    

> {
>       "name": "DV HDR10",
>       "includeCustomFormatWhenRenaming": false,
>       "specifications": [
>         {
>           "name": "DV HDR10",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": false,
>           "required": true,
>           "fields": {
>             "value": "^(?=.*\\b(DV|DoVi|Dolby[ .]?Vision)\\b)(?=.*\\b(HDR(10)?(P(lus)?)?)\\b)"
>           }
>         },
>         {
>           "name": "Not DV HLG",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(DV[ .]HLG)\\b"
>           }
>         },
>         {
>           "name": "Not DV SDR",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(DV[ .]SDR)\\b"
>           }
>         }
>       ]
>     }

- DV HLG

 

>    {
>       "name": "DV HLG",
>       "includeCustomFormatWhenRenaming": false,
>       "specifications": [
>         {
>           "name": "DV HLG",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": false,
>           "required": true,
>           "fields": {
>             "value": "\\b(DV[ .]HLG)\\b"
>           }
>         },
>         {
>           "name": "Not DV HDR10",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "^(?=.*\\b(DV|DoVi|Dolby[ .]?Vision)\\b)(?=.*\\b(HDR(10)?(P(lus)?)?)\\b)"
>           }
>         },
>         {
>           "name": "Not DV SDR",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(DV[ .]SDR)\\b"
>           }
>         }
>       ]
>     }

   - DV SDR 

    

> {
>       "name": "DV SDR",
>       "includeCustomFormatWhenRenaming": false,
>       "specifications": [
>         {
>           "name": "DV SDR",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": false,
>           "required": true,
>           "fields": {
>             "value": "\\b(DV[ .]SDR)\\b"
>           }
>         },
>         {
>           "name": "Not DV HDR10",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "^(?=.*\\b(DV|DoVi|Dolby[ .]?Vision)\\b)(?=.*\\b(HDR(10)?(P(lus)?)?)\\b)"
>           }
>         },
>         {
>           "name": "Not DV HLG",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(DV[ .]HLG)\\b"
>           }
>         }
>       ]
>     }

- FLAC

  

>   {
>       "name": "FLAC",
>       "includeCustomFormatWhenRenaming": false,
>       "specifications": [
>         {
>           "name": "FLAC",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": false,
>           "required": true,
>           "fields": {
>             "value": "\\bFLAC(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not PCM",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(l?)PCM(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not AAC",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bAAC(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not DTS",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bDTS(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not TrueHD/ATMOS",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "True[ .-]?HD|\\bATMOS(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not Basic Dolby Digital",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bDD[^a-z+]|(?<!e)ac3"
>           }
>         },
>         {
>           "name": "Not Dolby Digital Plus ",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bDD[P+]|\\b(e[-_. ]?ac3)\\b"
>           }
>         }
>       ]
>     }

- HDR 

   

>  {
>       "name": "HDR",
>       "includeCustomFormatWhenRenaming": false,
>       "specifications": [
>         {
>           "name": "HDR",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": false,
>           "required": true,
>           "fields": {
>             "value": "\\b(HDR)\\b"
>           }
>         },
>         {
>           "name": "Not DV",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(dv|dovi|dolby[ .]?vision)\\b"
>           }
>         },
>         {
>           "name": "Not HDR10",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bHDR10(\\b[^+|Plus])"
>           }
>         },
>         {
>           "name": "Not HDR10+",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bHDR10(\\+|P(lus)?\\b)"
>           }
>         },
>         {
>           "name": "Not HLG",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bHLG(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not PQ",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(PQ)\\b"
>           }
>         },
>         {
>           "name": "Not RlsGrp (Missing HDR)",
>           "implementation": "ReleaseGroupSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(FraMeSToR|HQMUX|SiCFoI)\\b"
>           }
>         },
>         {
>           "name": "Not SDR",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bSDR(\\b|\\d)"
>           }
>         }
>       ]
>     }

- HDR (undefined)

  

>   {
>       "name": "HDR (undefined)",
>       "includeCustomFormatWhenRenaming": false,
>       "specifications": [
>         {
>           "name": "RlsGrp (Missing HDR)",
>           "implementation": "ReleaseGroupSpecification",
>           "negate": false,
>           "required": true,
>           "fields": {
>             "value": "\\b(FraMeSToR|HQMUX|SiCFoI)\\b"
>           }
>         },
>         {
>           "name": "2160p",
>           "implementation": "ResolutionSpecification",
>           "negate": false,
>           "required": true,
>           "fields": {
>             "value": 2160
>           }
>         },
>         {
>           "name": "Not DV",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(dv|dovi|dolby[ .]?vision)\\b"
>           }
>         },
>         {
>           "name": "Not HDR10",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bHDR10(\\b[^+|Plus])"
>           }
>         },
>         {
>           "name": "Not HDR10+",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bHDR10(\\+|P(lus)?\\b)"
>           }
>         },
>         {
>           "name": "Not HLG",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(HLG)\\b"
>           }
>         },
>         {
>           "name": "Not PQ",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(PQ)\\b"
>           }
>         },
>         {
>           "name": "Not SDR",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bSDR(\\b|\\d)"
>           }
>         }
>       ]
>     }

- HDR10

  

>   {
>       "name": "HDR10",
>       "includeCustomFormatWhenRenaming": false,
>       "specifications": [
>         {
>           "name": "HDR10",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": false,
>           "required": true,
>           "fields": {
>             "value": "\\bHDR10(\\b[^+|Plus])"
>           }
>         },
>         {
>           "name": "Not DV HDR10",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "^(?=.*\\b(DV|DoVi|Dolby[ .]?Vision)\\b)(?=.*\\b(HDR(10)?(P(lus)?)?)\\b)"
>           }
>         },
>         {
>           "name": "Not PQ",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(PQ)\\b"
>           }
>         },
>         {
>           "name": "Not HLG",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(HLG)\\b"
>           }
>         },
>         {
>           "name": "Not SDR",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bSDR(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not DV",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(dv|dovi|dolby[ .]?vision)\\b"
>           }
>         }
>       ]
>     }

- HDR10+

>     {
>       "name": "HDR10+",
>       "includeCustomFormatWhenRenaming": false,
>       "specifications": [
>         {
>           "name": "HDR10+",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": false,
>           "required": true,
>           "fields": {
>             "value": "\\bHDR10(\\+|P(lus)?\\b)"
>           }
>         },
>         {
>           "name": "Not DV HDR10",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "^(?=.*\\b(DV|DoVi|Dolby[ .]?Vision)\\b)(?=.*\\b(HDR(10)?(P(lus)?)?)\\b)"
>           }
>         },
>         {
>           "name": "Not PQ",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(PQ)\\b"
>           }
>         },
>         {
>           "name": "Not HLG",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(HLG)\\b"
>           }
>         },
>         {
>           "name": "Not SDR",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bSDR(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not DV",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(dv|dovi|dolby[ .]?vision)\\b"
>           }
>         }
>       ]
>     }

- HDR10+ Boost

   

>  {
>       "name": "HDR10+ Boost",
>       "includeCustomFormatWhenRenaming": false,
>       "specifications": [
>         {
>           "name": "HDR10+",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": false,
>           "required": true,
>           "fields": {
>             "value": "\\bHDR10(\\+|P(lus)?\\b)"
>           }
>         },
>         {
>           "name": "Not DV HDR10",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "^(?=.*\\b(DV|DoVi|Dolby[ .]?Vision)\\b)(?=.*\\b(HDR(10)?(P(lus)?)?)\\b)"
>           }
>         },
>         {
>           "name": "Not PQ",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(PQ)\\b"
>           }
>         },
>         {
>           "name": "Not HLG",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(HLG)\\b"
>           }
>         },
>         {
>           "name": "Not SDR",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bSDR(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not DV",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(dv|dovi|dolby[ .]?vision)\\b"
>           }
>         }
>       ]
>     }

- HLG

   

>  {
>       "name": "HLG",
>       "includeCustomFormatWhenRenaming": false,
>       "specifications": [
>         {
>           "name": "HLG",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": false,
>           "required": true,
>           "fields": {
>             "value": "\\b(HLG)\\b"
>           }
>         },
>         {
>           "name": "Not DV",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(dv|dovi|dolby[ .]?vision)\\b"
>           }
>         },
>         {
>           "name": "Not HDR10+",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bHDR10(\\+|P(lus)?\\b)"
>           }
>         },
>         {
>           "name": "Not HDR10",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bHDR10(\\b[^+|Plus])"
>           }
>         },
>         {
>           "name": "Not PQ",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(PQ)\\b"
>           }
>         }
>       ]
>     }

- NO DV

   

>  {
>       "name": "NO DV",
>       "includeCustomFormatWhenRenaming": false,
>       "specifications": [
>         {
>           "name": "DV",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(dv|dovi|dolby[ .]?vision)\\b"
>           }
>         },
>         {
>           "name": "Not DV HDR10",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "^(?=.*\\b(DV|DoVi|Dolby[ .]?Vision)\\b)(?=.*\\b(HDR(10)?(P(lus)?)?)\\b)"
>           }
>         },
>         {
>           "name": "Not DV HLG",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(DV[ .]HLG)\\b"
>           }
>         },
>         {
>           "name": "Not DV SDR",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(DV[ .]SDR)\\b"
>           }
>         }
>       ]
>     }

- PCM 

   

>  {
>       "name": "PCM",
>       "includeCustomFormatWhenRenaming": false,
>       "specifications": [
>         {
>           "name": "PCM",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": false,
>           "required": true,
>           "fields": {
>             "value": "\\b(l?)PCM(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not AAC",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bAAC(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not FLAC",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bFLAC(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not DTS",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bDTS(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not TrueHD/ATMOS",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "True[ .-]?HD|\\bATMOS(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not Basic Dolby Digital",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bDD[^a-z+]|(?<!e)ac3"
>           }
>         },
>         {
>           "name": "Not Dolby Digital Plus ",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bDD[P+]|\\b(e[-_. ]?ac3)\\b"
>           }
>         }
>       ]
>     }

- PQ

    

> {
>       "name": "PQ",
>       "includeCustomFormatWhenRenaming": false,
>       "specifications": [
>         {
>           "name": "PQ",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": false,
>           "required": true,
>           "fields": {
>             "value": "\\b(PQ)\\b"
>           }
>         },
>         {
>           "name": "Not DV",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(dv|dovi|dolby[ .]?vision)\\b"
>           }
>         },
>         {
>           "name": "Not HDR10+",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bHDR10(\\+|P(lus)?\\b)"
>           }
>         },
>         {
>           "name": "Not HDR10",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bHDR10(\\b[^+|Plus])"
>           }
>         },
>         {
>           "name": "Not HLG",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(HLG)\\b"
>           }
>         },
>         {
>           "name": "Not SDR",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bSDR(\\b|\\d)"
>           }
>         }
>       ]
>     }

- TrueHD

   

>  {
>       "name": "TrueHD",
>       "includeCustomFormatWhenRenaming": false,
>       "specifications": [
>         {
>           "name": "TrueHD",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": false,
>           "required": true,
>           "fields": {
>             "value": "True[ .-]?HD"
>           }
>         },
>         {
>           "name": "ATMOS",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bATMOS(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not Dolby Digital Plus",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bDD[P+]|\\b(e[-_. ]?ac3)\\b"
>           }
>         },
>         {
>           "name": "Not DTS",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bDTS(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not FLAC",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bFLAC(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not Basic Dolby Digital",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bDD[^a-z+]|(?<!e)ac3"
>           }
>         },
>         {
>           "name": "Not RlsGrp (TrueHD only)",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "CtrlHD|W4NK3R|\\bDON\\b"
>           }
>         }
>       ]
>     }

-TrueHD ATMOS

   

>  {
>       "name": "TrueHD ATMOS",
>       "includeCustomFormatWhenRenaming": false,
>       "specifications": [
>         {
>           "name": "TrueHD",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": false,
>           "required": true,
>           "fields": {
>             "value": "True[ .-]?HD|W4NK3R|HQMUX"
>           }
>         },
>         {
>           "name": "ATMOS",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": false,
>           "required": true,
>           "fields": {
>             "value": "\\b(ATMOS|CtrlHD|W4NK3R|DON)(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not Basic Dolby Digital",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bDD[^a-z+]|(?<!e)ac3"
>           }
>         },
>         {
>           "name": "Not Dolby Digital Plus ",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bDD[P+]|\\b(e[-_. ]?ac3)\\b"
>           }
>         },
>         {
>           "name": "Not DTS",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bDTS(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not DTS X",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\b(dts[-_. ]?x)\\b(?!\\d)"
>           }
>         },
>         {
>           "name": "Not FLAC",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": "\\bFLAC(\\b|\\d)"
>           }
>         }
>       ]
>     }

- x265 (HD)

   

>  {
>       "name": "x265 (HD)",
>       "includeCustomFormatWhenRenaming": false,
>       "specifications": [
>         {
>           "name": "x265/HEVC",
>           "implementation": "ReleaseTitleSpecification",
>           "negate": false,
>           "required": true,
>           "fields": {
>             "value": "[xh][ ._-]?265|\\bHEVC(\\b|\\d)"
>           }
>         },
>         {
>           "name": "Not 2160p",
>           "implementation": "ResolutionSpecification",
>           "negate": true,
>           "required": true,
>           "fields": {
>             "value": 2160
>           }
>         }
>       ]
>     }
