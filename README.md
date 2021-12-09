# Movie review sentimental analysis and word cloud

### 네이버 영화 리뷰 감성분석 및 워드클라우드

folder1. movie: 네이버 영화에서 크롤링한 영화 리뷰 데이터

    [title, link, score, review]
    
folder2. sentiment: 영화리뷰 감성분석 시행 수 감성점수 포함된 리뷰 데이터

    [title, link, score, review, sentiment]


1. Movie Crawling
    - 네이버 영화 '네티즌 평점' 탭에서의 리뷰 크롤링
    - https://movie.naver.com/movie/point/af/list.naver

1. Movie Crawling Mainpage
    - 네이버 영화의 각 영화 상세페이지 평점 탭의 크롤링
    - Chrom의 경우 F12 DevTool의 Network탭에서 리뷰 데이터를 가져오는 주소를 확인 후 해당 페이지에서 크롤링 한다
    - ex) 19곰 테드: https://movie.naver.com/movie/bi/mi/pointWriteFormList.naver?code=80707&type=after&isActualPointWriteExecute=false&isMileageSubscriptionAlready=false&isMileageSubscriptionReject=false&page=1

2. Movie File Merge
    - 크롤링 된 여러개의 리뷰 데이터 파일을 하나의 파일로 합침

3. Crawling Data Repetition Check
    - 크롤링된 리뷰 중 중복 데이터가 존재하는지 확인
    - 필요시 중복 데이터 제거

4. Movie Review Sentimental Analysis
    - 영화 리뷰 감성분석
    - LSTM을 사용하여 영화 리뷰의 긍정/부정 여부를 예측한다

5. Review All Wordcloud
    - 크롤링한 영화 리뷰 데이터를 사용한 워드클라우드 생성
    - 불용어 선정에 있어서는 개인의 의견이 반영될 수 있다

6. Review Positive Negative Wordcloud
    - 긍정 영화 리뷰와 부정 영화 리뷰 데이터를 사용한 워드클라우드 생성
    - 긍정 영화 리뷰는 감성점수 0.8이상, 네티즌 평점 3이상이고, 부정 영화 리뷰는 감성점수 0.2이하, 네티즌 평점 7이하이다
    - 이는 반어법적 표현 등 알고리즘이 파악할 수 없는 감성점수와 평점의 부조화를 피하기 위함이다
    - 불용어 선정에 있어서는 개인의 의견이 반영될 수 있다

7. Movie Sentiment Average and Similarity
    - 영화 리뷰 감성점수와 네티즌 평점 사이 상관관계 계산
    - 계산식은 코사인 유사도(cosine similarity)를 사용
    - 무작위 선정된 5개 영화의 평점 평균과 감성점수 평균을 계산, 분석
