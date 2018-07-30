# Snowball

Before Snowball there was AWS Import Export Disk (bypassing the internet).
Snowball is petabyte-scale data transport solution, that uses secure appliances to transfer large amounts of data in and out of AWS cloud.

- Snowball Standard
- Snowball Edge - (Can also run Lambda functions)
- Snowmobile (Exabyte-scale container pulled by a truck)

Snowball can:

- Import to S3
- Export from S3

If you are using Glacier, you have to **restore to S3 from Glacier** and then use Snowball.
