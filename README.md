# FMDBplus
Add method which can executeUpdateFromFile
-(void) executeUpdateFromFile:(FMDatabase *)sample fileName:(NSString*)name type:(NSString*)type
{
    NSString * createtablePath = [[NSBundle bundleForClass:[self class]] pathForResource:name ofType:type];
    NSString *initDBS=[NSString stringWithContentsOfFile:createtablePath encoding:NSUTF8StringEncoding error:nil];
    sqlite3_exec([sample sqliteAddr:sample],[initDBS UTF8String],NULL,NULL,nil);
}
