---
name: Home
assetId: 956461b8-2daa-4062-9be8-d039495d49c0
type: page
---

# Welcome

This is your new project's homepage. Edit this file to get started.

'''
select County_Name, Count(*)
from mping
group by County_Name
ORDER BY County_Name
'''