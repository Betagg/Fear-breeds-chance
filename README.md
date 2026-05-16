# SPY / QQQ 与 CNN Fear & Greed 十年走势图

这是一个可直接部署到 GitHub Pages 的静态网站。

## 内容

- `index.html`：独立走势图页面，内嵌十年曲线数据，无需后端。
- `data/fear-greed-trend-series-2026-05-16.json`：原始曲线数据，便于后续复用或二次分析。
- `.github/workflows/pages.yml`：GitHub Pages 自动部署工作流。

## 图表口径

- 横轴：时间，2016-05-16 至 2026-05-15。
- 左轴：SPY 与 QQQ 前复权价格走势。
- 右轴：CNN Fear & Greed 指数，0-100。
- 红色背景区：Fear & Greed 小于等于 30 的恐惧区域。
- SPY 代理标普 500，QQQ 代理纳指/纳斯达克风险资产。

## 数据源

- SPY / QQQ：Futu OpenD 前复权日线。
- Fear & Greed：`whit3rabbit/fear-greed-data` 的历史归档；该仓库说明 CNN 官方不提供完整历史数据，2021-02-01 以后由 CNN endpoint 自动刷新。

## 本地预览

直接打开 `index.html` 即可，或在本目录运行：

```bash
python3 -m http.server 8080
```

然后访问：

```text
http://127.0.0.1:8080/
```

## GitHub Pages 部署

推送到 GitHub 后，在仓库 `Settings -> Pages` 中选择 GitHub Actions。工作流会自动发布根目录的静态文件。

