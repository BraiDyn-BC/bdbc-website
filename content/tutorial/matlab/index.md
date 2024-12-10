---
title: "MATLAB Tutorial: NWBからPeri-Event Time Histogram作成"
date: 2024-12-05T22:10:39+09:00
draft: false
tags: [Tutorial, MATLAB]
description: セッションのメタデータの表示，トライアル情報の取り込み・表示，神経活動の読み込み・表示および各トライアルで提示される音刺激にPeri-event time histogram（PETH）の作成・表示，生データ（5kHzサンプリング）の取り出し・表示・PETH作成，DeepLabCutで推定されたキーポイントおよび瞳孔経の読み出し・表示・PETH作成などを行う簡単なプログラム
---

# MATLAB Tutorial: NWBからPeri-Event Time Histogram作成

**MATLABを利用する場合、[Sample：オペラント条件づけの学習](BraiDyn-BC%20Database%201e972fb17ad1470b911aa108fb8c0713/BraiDyn-BC%20Database%20e0b7915fe8a848338ad5b864cf62e07a/Sample%EF%BC%9A%E3%82%AA%E3%83%98%E3%82%9A%E3%83%A9%E3%83%B3%E3%83%88%E6%9D%A1%E4%BB%B6%E3%81%A4%E3%82%99%E3%81%91%E3%81%AE%E5%AD%A6%E7%BF%92%E9%81%8E%E7%A8%8B%207406ca6719fe4827bfaa0a7fbcdf4baa.md)のデータをローカル環境にダウンロードのうえ、PATHを設定し以下を実行してください。**

[BraiDynDB_handlingSampleData.m](https://www.dropbox.com/scl/fi/fzws8va5y6xq8kzyvyj3c/BraiDynDB_handlingSampleData.m?rlkey=aofn0pyeziccivwwxgaonjywr&dl=0)

## Data usage (NWBの読み込み，PETH作成方法など)

※本サンプルデータ公開時点では，matlabを用いたNWBファイル読み込み・PETH作成方法を記述したサンプルコードを公開する．全データ公開時においては，pythonによるNWBファイルの読み込み・PETH作成についてのドキュメントもあわせて公開予定．

1. NWBファイルをmatlabから取り扱うための関数群であるMatNWBを，以下のGithubページ（[https://neurodatawithoutborders.github.io/matnwb/](https://neurodatawithoutborders.github.io/matnwb/)）の指示に従いセットアップする．
2. サンプルデータセットをダウンロードする．
3. デモコード（BraiDynDB_handlingSampleData.m）内，*nwbpath*を読み込みたいnwbファイルへのパスに置き換える．

セッションのメタデータの表示，トライアル情報の取り込み・表示，神経活動の読み込み・表示および各トライアルで提示される音刺激にPeri-event time histogram（PETH）の作成・表示，生データ（5kHzサンプリング）の取り出し・表示・PETH作成，DeepLabCutで推定されたキーポイントおよび瞳孔経の読み出し・表示・PETH作成などを行う簡単なプログラム

1. MatNWBについてのより詳細な使用法，およびドキュメントについては以下のURLを参照のこと．
- [Reading NWB Data in MATLAB](https://neurodatawithoutborders.github.io/matnwb/tutorials/html/read_demo.html#H_01DD834C)
- [Introduction to MatNWB](https://neurodatawithoutborders.github.io/matnwb/tutorials/html/intro.html)