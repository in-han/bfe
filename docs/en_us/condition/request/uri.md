# Request URI Related Primitives

## req_host_in(host_list)
* Description: Judge if host matches configured patterns

* Parameters

| Parameter | Descrption |
| --------- | ---------- |
| host_list | String<br>a list of hosts keys which are concatenated using &#124;<br>case insensitive |

* Example

```
# right：
req_host_in("www.bfe-networks.com|bfe-networks.com")

# wrong：
req_host_in("www.bfe-networks.com | bfe-networks.com")
```

## req_path_in(path_list, case_insensitive)
* Description: Judge if request path matches configured patterns

* Parameters

| Parameter | Descrption |
| --------- | ---------- |
| path_list | String<br>a list of paths which are concatenated using &#124; |
| case_insensitive | Boolean<br>case insensitive |

* Example

```
req_path_in("/api/search|/api/list", true)
```

## req_path_prefix_in(prefix_list, case_insensitive)
* Description: Judge if request path prefix matches configured patterns

* Parameters

| Parameter | Descrption |
| --------- | ---------- |
| prefix_list | String<br>a list of path prefixs which are concatenated using &#124; |
| case_insensitive | Boolean<br>case insensitive |

* Example

```
req_path_prefix_in("/api/report|/api/analytics", false)
```
    
## req_path_suffix_in(suffix_list, case_insensitive)
* Description: Judge if request path suffix matches configured patterns

* Parameters

| Parameter | Descrption |
| --------- | ---------- |
| suffix_list | String<br>a list of path sufixs which are concatenated using &#124; |
| case_insensitive | Boolean<br>case insensitive |

* Example

```
req_path_suffix_in(".php|.jsp", false)
```

**Note:**
**The patterns of req_path_in and req_path_prefix_in need to be included "/"**

## req_query_key_in(key_list)
* Description: Judge if query key matches configured patterns

* Parameters

| Parameter | Descrption |
| --------- | ---------- |
| key_list | String<br>a list of query keys which are concatenated using &#124; |

* Example

```
req_query_key_exist("word|wd")
```

## req_query_key_prefix_in(prefix_list)
* Description: Judge if query key prefix matches configured patterns

* Parameters

| Parameter | Descrption |
| --------- | ---------- |
| prefix_list | String<br>a list of query key prefixs which are concatenated using &#124; |


* Example

```
req_query_key_prefix_in("rid")
```

## req_query_value_in(key, value_list, case_insensitive)
* Description: Judge if value of query key matches configured patterns

* Parameters

| Parameter | Descrption |
| --------- | ---------- |
| key | String<br> query key |
| value_list | String<br>a list of query values which are concatenated using &#124; |
| case_insensitive | Boolean<br>case insensitive |

* Example

```
req_query_value_in("uid", "x|y|z", true)
```

## req_query_value_prefix_in(key, prefix_list, case_insensitive)
* Description: Judge if value prefix of query key matches configured patterns

* Parameters

| Parameter | Descrption |
| --------- | ---------- |
| key | String<br> query key |
| value_list | String<br>a list of query value prefixs which are concatenated using &#124; |
| case_insensitive | Boolean<br>case insensitive |

* Example

```
req_query_value_prefix_in("uid", "100|200", true)
```

## req_query_value_suffix_in(key, suffix_list, case_insensitive)
* Description: Judge if value suffix of query key matches configured patterns

* Parameters

| Parameter | Descrption |
| --------- | ---------- |
| key | String<br> query key |
| suffix_list | String<br>a list of query value suffixs which are concatenated using &#124; |
| case_insensitive | Boolean<br>case insensitive |

* Example

```
req_query_value_suffix_in("uid", "1|2|3", true)
```

## req_query_value_hash_in(key, value_list, case_insensitive)
* Descrption: Judge if the hash value of specified query matches configured patterns (value after hash is 0～9999)

* Parameters

| Parameter | Descrption |
| --------- | ---------- |
| key | String<br> query key |
| value_list | String<br>a list of hash values which are concatenated using &#124; |
| case_insensitive | Boolean<br>case insensitive |

* Example

```
req_query_value_hash_in("cid", "100", true)
```

## req_port_in(port_list)
* Description: Judge if port matches configured patterns

* Parameters

| Parameter | Descrption |
| --------- | ---------- |
| port_list | String<br>a list of ports which are concatenated using &#124; |


* Example

```
req_port_in("80|8080")
```

## req_url_regmatch(reg_exp)
* Description: patterns is regular expression to match url

* Parameters

| Parameter | Descrption |
| --------- | ---------- |
| reg_exp | String<br>a regular expression<br> It is recommended that use `` to avoid from character escaping |

* Example

```
req_url_regmatch(`/s\?word=123`)
```
