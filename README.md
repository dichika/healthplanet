# healthplanet [![CRAN Version](http://www.r-pkg.org/badges/version/healthplanet)](http://cran.rstudio.com/web/packages/healthplanet)

healthplanetパッケージは[Tanita](http://www.tanita.co.jp/)により運営・提供されている[Health Planet API](https://www.healthplanet.jp/apis/api.html)のラッパーパッケージです。
[Health Planet API](https://www.healthplanet.jp/apis/api.html)で取得できるデータをRのdata.frame形式で返却します。
(※現在、innerscan系のデータのみ)

## 使用する前に下記の登録が必要です
- [HealthPlanet](https://www.healthplanet.jp/)への会員登録
- 会員登録後、[HealthPlanet](https://www.healthplanet.jp/)にログインし、アプリケーションの登録を行い、「Client ID」と「Client secret」を取得

## パッケージのインストール

healthplanetパッケージはCRANにはありませんが、Githubより以下のコマンドでインストール可能です。
```R
install.packages("devtools")
devtools::install_github("teramonagi/healthplanet")
```

## 使用例
```R
> client_id <- "<your own client id>"
> client_secret <- "<your own client secret>"
> user_id <- "<HealthPlanetのID>"
> user_password <- "<HealthPalentのパスワード>"
> access_token <- getToken(user_id, user_password, client_id, client_secret)
> df <- getInnerScan(access_token)
> df
   sex birth_date heght                date    model basal_metabolic_rate body_age body_fat bone_mass muscle_mass muscle_score visceral_fat_level weight
1 male 1963-03-10   180 2016-03-16 06:49:00 01000099                 1685       43     20.9       3.1       56.70            0                9.5  75.60
2 male 1963-03-10   180 2016-03-17 08:04:00 01000099                 1705       44     21.4       3.1       57.30            0               10.0  76.85
3 male 1963-03-10   180 2016-03-18 05:48:00 01000099                 1677       44     21.2       3.1       56.45            0                9.5  75.55
4 male 1963-03-10   180 2016-03-19 07:11:00 01000099                 1667       44     21.2       3.1       56.15            0                9.5  75.15
5 male 1963-03-10   180 2016-03-20 06:39:00 01000099                 1687       43     20.5       3.1       56.80            0                9.5  75.35
6 male 1963-03-10   180 2016-03-21 05:28:00 01000099                 1675       43     20.7       3.1       56.40            0                9.5  75.00
```
